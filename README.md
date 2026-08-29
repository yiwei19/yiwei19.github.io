# Yi Wei — Personal Website

线上地址：https://yiwei19.github.io

学术主页 + 博客。GitHub Pages 自带的 Jekyll 负责构建 —— **本地不需要装任何东西**，
push 上去 1–2 分钟后自动生效。

## 怎么更新

**内容和外观是分开的。** 日常只改 `_data/` 里的 YAML 和 `_posts/` 里的 Markdown，
不用碰 HTML 和 CSS。

👉 **[docs/README.md](docs/README.md) 是所有更新指南的入口**，每个板块一份。

| 板块 | 改哪个文件 |
|---|---|
| 头像 / 姓名 / 联系方式 / 自我介绍 | `_data/bio.yml` |
| News | `_data/news.yml` |
| Publications | `_data/publications.yml` |
| Projects | `_data/projects.yml` |
| Experience | `_data/experience.yml` |
| Teaching | `_data/teaching.yml` |
| Education | `_data/education.yml` |
| Awards & Honors | `_data/awards.yml` |
| 博客文章 | `_posts/` 里新建 `.md` |

空的板块会自动从主页上隐藏。

## 目录结构

```
_config.yml           站点设置
_data/                所有内容（← 你日常改这里）
_posts/               博客文章（Markdown）
_layouts/             页面骨架
_includes/            每个板块的 HTML 模板
assets/               图片、视频、CV
  css/style.css       全站样式
docs/                 更新指南（← 从这里开始看）
index.html            主页（只有一行 front matter，内容都来自 _data/）
blog.html             博客列表页
```

## 发布

```bash
cd ~/Documents/career/website
git add -A
git commit -m "写清楚改了什么"
git push
```

排错见 [docs/deploy.md](docs/deploy.md)。

## 待办

- [ ] 补 `assets/Yi_Wei_CV.pdf`，然后在 `_data/bio.yml` 里取消注释 CV 链接
- [ ] 删掉示例博客文章 `_posts/2026-08-29-how-this-blog-works.md`，换成真的第一篇
- [ ] model-based RL / 约束搜索空间方向有产出后，填 `_data/projects.yml`
- [ ] 简历页眉加一行网站地址
