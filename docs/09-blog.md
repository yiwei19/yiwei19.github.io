# Blog

**新建文件：** `_posts/YYYY-MM-DD-some-slug.md`
**显示在：** https://yiwei19.github.io/blog/

博客文章用 Markdown 写，不碰任何 HTML。文件名里的日期决定排序，front matter 里的
`title` 决定显示的标题。

## 发一篇新文章

### 1. 建文件

文件名格式是**死的**，写错了 Jekyll 会直接忽略这个文件：

```
_posts/2026-11-04-hand-eye-calibration-bug.md
     └──日期──┘ └──────── slug ────────┘
```

- 日期必须是 `YYYY-MM-DD`，四位年、两位月、两位日
- slug 全小写，单词之间用连字符 `-`，**不要空格、不要中文**
- 扩展名必须是 `.md`
- slug 会成为网址：`/blog/2026/11/04/hand-eye-calibration-bug/`

### 2. 写 front matter

文件**必须**以两行 `---` 之间的这一段开头：

```markdown
---
title: "The 30 mm that wasn't there"
description: "A hand-eye calibration bug that looked like sensor noise for two weeks."
---

正文从这里开始。
```

| 字段 | 必填 | 说明 |
|---|---|---|
| `title` | 是 | 显示的标题。**有冒号就加引号** |
| `description` | 否 | 列表页上标题下面那句话。不写的话自动截取正文前 180 字 |

### 3. 写正文

普通 Markdown。`_posts/2026-08-29-how-this-blog-works.md` 那篇本身就是格式参考，
写第一篇真文章之前可以照着抄，写完了就把它删掉。

插图：图片放 `assets/`，正文里用**根路径**引用：

```markdown
![说明文字](/assets/calibration-error.png)
```

写 `![](assets/xxx.png)`（少了开头的斜杠）在文章页里会 404。

### 4. 上线

```bash
cd ~/Documents/career/website
git add -A
git commit -m "blog: hand-eye calibration post"
git push
```

等 1–2 分钟，文章自动出现在 `/blog/` 列表最上面 —— **不需要手动改列表页**。

## 改已经发布的文章

直接改那个 `.md` 文件，再 push 一次。想改网址就改文件名（旧网址会失效，
如果已经分享出去了就别改）。

## 撤下一篇文章

两个办法：

- **彻底删掉**：删文件，push。
- **留着但不发布**：在 front matter 里加 `published: false`，文件还在但不会出现在网站上。

## 写作建议

你说要写科研日常、思考、技术笔记、论文精读。几个经验：

- **一篇只讲一件事。** 400 字讲透一个真问题，胜过 2000 字的综述。
- **写你卡住过的地方。** "这个数字为什么不对、我是怎么发现的、最后是什么原因" ——
  这类文章最有人看，也最能体现判断力。
- **`description` 要认真写。** 列表页上人只看标题和这一句，决定要不要点进去。
- **日期用你真正写的那天。** 这个博客将来是你的时间线，日期造假没意义。
