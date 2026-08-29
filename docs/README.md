# 更新指南

网站的**内容**和**外观**是分开的。你日常只需要改 `_data/` 里的 YAML 文件和 `_posts/` 里的
Markdown 文件 —— 从来不用碰 HTML 或 CSS。

## 每个板块改哪个文件

| 板块 | 改这个文件 | 指南 |
|---|---|---|
| 头像 / 姓名 / 联系方式 / 自我介绍 | `_data/profile.yml` | [01-bio.md](01-bio.md) |
| News | `_data/news.yml` | [02-news.md](02-news.md) |
| Publications | `_data/publications.yml` | [03-publications.md](03-publications.md) |
| Projects | `_data/projects.yml` | [04-projects.md](04-projects.md) |
| Experience | `_data/experience.yml` | [05-experience.md](05-experience.md) |
| Teaching | `_data/teaching.yml` | [06-teaching.md](06-teaching.md) |
| Education | `_data/education.yml` | [07-education.md](07-education.md) |
| Awards & Honors | `_data/awards.yml` | [08-awards.md](08-awards.md) |
| Blog 文章 | `_posts/` 里新建 `.md` | [09-blog.md](09-blog.md) |
| 上线 / 排错 | — | [10-deploy.md](10-deploy.md) |

**空板块会自动隐藏。** Projects、Teaching、Awards 现在是空的，所以主页上看不到它们；
往对应的 YAML 里加第一条，板块就自己出现了。板块顺序固定为
Bio → News → Publications → Projects → Experience → Teaching → Education → Awards。

## 三分钟看懂 YAML

所有 `_data/*.yml` 都是同一种格式：一个列表，每条前面一个 `-`。

```yaml
- role: Undergraduate Researcher      # 一条的开始，用 "- " 起头
  org: Purdue University              # 同一条的其他字段，缩进 2 个空格对齐
  period: 2026–present

- role: Research Intern               # 空一行，下一条
  org: Somewhere Else
  period: Summer 2027
```

四条规则，违反了页面就不更新：

1. **缩进只用空格，永远不要用 Tab。** 同一条里的字段全部对齐到同样的缩进。
2. **值里有冒号就加引号**：`title: "MeanFlow: a fast sampler"`，不然 YAML 会当成新字段。
3. **长段落用 `>`**，然后换行缩进写，YAML 会把它折成一个自然段：
   ```yaml
   summary: >
     第一行。
     第二行会接在第一行后面，成为同一段。
   ```
4. **可以写 HTML**：`<b>粗体</b>`、`<i>斜体</i>`、`<a href="...">链接</a>` 在正文字段里都有效。

## 改完怎么上线

```bash
cd ~/Documents/career/website
git add -A
git commit -m "写清楚改了什么"
git push
```

等 1–2 分钟，刷新 https://yiwei19.github.io（Cmd+Shift+R 强制刷新）。
出问题看 [10-deploy.md](10-deploy.md)。
