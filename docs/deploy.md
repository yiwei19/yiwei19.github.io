# 上线与排错

## 日常流程

```bash
cd ~/Documents/career/website
git add -A
git commit -m "写清楚改了什么"
git push
```

等 1–2 分钟，**Cmd+Shift+R** 强制刷新 https://yiwei19.github.io。
普通刷新会拿到 CDN 缓存里的旧版本。

## 这个网站怎么构建的

GitHub Pages 自带 Jekyll。你 push 之后，GitHub 在服务器上：

1. 读 `_config.yml`
2. 读 `_data/*.yml`，把内容灌进 `_layouts/` 和 `_includes/` 里的模板
3. 把 `_posts/*.md` 转成文章页
4. 生成静态网站发布出去

**你的电脑上不需要装任何东西**，也不需要本地构建。`_site/` 这种目录不会出现在你的
文件夹里（真出现了也已经被 `.gitignore` 忽略了）。

## 哪些文件能改，哪些别碰

| 目录 | 是什么 | 你改吗 |
|---|---|---|
| `_data/` | **所有内容** | ✅ 日常就改这里 |
| `_posts/` | 博客文章 | ✅ |
| `assets/` | 图片、视频、CV | ✅ 往里放文件 |
| `docs/` | 就是你正在看的这些指南 | ✅ 随便改 |
| `_includes/` | 每个板块的 HTML 模板 | ⚠️ 想改版式再动 |
| `_layouts/` | 页面骨架 | ⚠️ |
| `assets/css/style.css` | 全站样式 | ⚠️ |
| `_config.yml` | 站点设置 | ⚠️ 改完必须 push 才生效 |

## push 被拒绝

```
! [rejected]  main -> main (fetch first)
```

远端有你本地没有的 commit —— 基本都是因为你在 GitHub 网页上改过东西。

```bash
git pull
git push
```

（已经设过 `pull.rebase true`，所以 `git pull` 是干净的 rebase。）

如果 `git pull` 报 conflict：`git status` 看是哪个文件，打开找 `<<<<<<<` 和 `>>>>>>>`
之间的两个版本，留下你要的那份、删掉标记行，然后：

```bash
git add 那个文件
git rebase --continue
```

## push 中途断掉 / HTTP 400

```
error: RPC failed; HTTP 400 curl 22 The requested URL returned error: 400
send-pack: unexpected disconnect while reading sideband packet
fatal: the remote end hung up unexpectedly
```

**跟网络没关系，是 git 的缓冲区太小。** git 通过 HTTPS 推送时默认只有 1 MiB 的
`http.postBuffer`，一旦这次 push 的总体积超过它（比如带了一个视频），连接就会被掐断。
注意结尾那句 `Everything up-to-date` 是假象 —— 什么都没推上去。

这个仓库已经设好了，正常不会再遇到。**万一在别的机器上克隆后又碰到，跑这两行：**

```bash
git config http.postBuffer 524288000    # 500 MB
git config http.version HTTP/1.1        # 绕开 macOS 上 HTTP/2 的一个已知问题
git push
```

还是不行的话，把大文件那次 commit 单独先推，减小单次体积：

```bash
git log --oneline          # 找到中间那次 commit 的 hash
git push origin <hash>:main
git push
```

## push 成功了但网站没更新

按顺序查：

1. **Cmd+Shift+R** 强制刷新
2. 去仓库页面点 **Actions** 标签，看最新那次 `pages build and deployment`
   - 🟡 还在跑 —— 等一分钟
   - ✅ 绿勾 —— 构建成功，是缓存问题，换个浏览器或无痕窗口试试
   - ❌ 红叉 —— **构建失败了，看下面**

## 构建失败了

好消息：**构建失败时 GitHub Pages 会继续提供上一个成功的版本**，网站不会挂掉，
只是你的新改动没生效。GitHub 也会给你发一封邮件说明原因。

点开 Actions 里那次红叉的日志，几乎所有失败都是 YAML 写错了：

| 报错里出现 | 原因 | 怎么修 |
|---|---|---|
| `did not find expected key` | 缩进不对，或者混用了 Tab | 同一条的字段全部对齐到 2 个空格；把 Tab 换成空格 |
| `mapping values are not allowed` | 值里有没加引号的冒号 | `title: "MeanFlow: fast sampling"` |
| `could not find expected ':'` | 少了 `- ` 或者字段名后面少了冒号 | 对照 `docs/` 里的模板检查 |
| 提到某个 `.md` 文件 | 文章的 front matter 坏了 | 检查开头那两行 `---`，以及 `title` 有冒号是否加了引号 |

**push 之前自查 YAML**（在网站文件夹里跑）：

```bash
python3 -c "
import yaml, glob
for f in sorted(glob.glob('_data/*.yml')):
    try:
        yaml.safe_load(open(f)); print('OK  ', f)
    except Exception as e:
        print('BAD ', f, e)
"
```

全是 `OK` 就可以放心 push。

## 想回退到上一个版本

```bash
git log --oneline        # 找到你想回到的那次 commit
git revert <那个commit之后的commit>
git push
```

`git revert` 是**新建一个撤销的 commit**，比 `git reset` 安全 —— 历史不会被改写，
远端也不会拒绝。
