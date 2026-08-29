# Bio —— 头像、姓名、联系方式、自我介绍

**改这个文件：** `_data/bio.yml`
**显示在：** 主页最上面那一块（永远显示，不能隐藏）

## 改自我介绍

`bio:` 下面每一条 `- ` 就是一个自然段，按顺序显示。

```yaml
bio:
  - text: >
      没有 label 的段落就是普通正文。
  - label: Goal
    text: 有 label 的段落会在开头显示一个粗体小标题，后面跟一个冒号。
  - label: Currently
    muted: true
    text: 加上 muted 会让整段变成灰色，适合放"正在做什么"这种时效性内容。
```

| 字段 | 必填 | 说明 |
|---|---|---|
| `text` | 是 | 段落正文。可以写 HTML（链接、粗体）。 |
| `label` | 否 | 段首的粗体小标题，自动加冒号 |
| `muted` | 否 | `true` 时整段变灰 |

## 改联系方式链接

```yaml
links:
  - label: Email
    url: mailto:wei577@purdue.edu
  - label: GitHub
    url: https://github.com/yiwei19
```

删掉一整条（两行）就是移除那个链接，加一条就是新增。**CV 和 Google Scholar 的两条
已经写好但被注释掉了** —— 把行首的 `#` 删掉就能启用：

```yaml
  - label: CV
    url: /assets/Yi_Wei_CV.pdf
```

启用 CV 之前，先把 PDF 放进 `assets/` 并确认文件名完全一致，否则点击是 404。

## 换头像

把新照片存成 `assets/profile.jpg`（覆盖旧的），文件名不用改。

- **正方形裁剪最好** —— 网页上会裁成正方形显示
- 如果脸的位置偏了，改 `assets/css/style.css` 里这一行的第二组数字：
  ```css
  .intro .portrait img { ... object-position: 53% 45%; }
  ```
  第一个百分比是水平（越大越往右），第二个是垂直（越小越往上）。

## 改姓名

```yaml
name: Yi Wei          # 英文名，同时用在导航栏和页脚
name_cn: 危伊         # 中文名，显示在英文名右边、小一号的灰字
```

删掉 `name_cn` 那一行，中文名就不显示。
