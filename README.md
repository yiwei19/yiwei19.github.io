# Yi Wei — Personal Website

Live at: https://yiwei19.github.io

Academic homepage + blog. GitHub Pages builds it with its built-in Jekyll, so
**nothing needs to be installed locally**. Changes go live 1–2 minutes after a push.

## How to update

**Content and appearance are kept separate.** Day to day, you only edit the YAML in
`_data/` and the Markdown in `_posts/`; there's no need to touch HTML or CSS.

👉 **[docs/README.md](docs/README.md) is the entry point for all update guides**, one per section.

| Section | File to edit |
|---|---|
| Photo / name / contact / bio | `_data/bio.yml` |
| News | `_data/news.yml` |
| Publications | `_data/publications.yml` |
| Projects | `_data/projects.yml` |
| Experience | `_data/experience.yml` |
| Teaching | `_data/teaching.yml` |
| Service | `_data/service.yml` |
| Education | `_data/education.yml` |
| Awards & Honors | `_data/awards.yml` |
| Blog posts (currently hidden, see [docs/blog.md](docs/blog.md)) | new `.md` file in `_posts/` |

Empty sections are hidden from the homepage automatically.

## Directory layout

```
_config.yml           site settings
_data/                all content (← edit here day to day)
_posts/               blog posts (Markdown)
_layouts/             page skeletons
_includes/            HTML template for each section
assets/               images, videos, resume
  css/style.css       site-wide styles
docs/                 update guides (← start here)
index.html            homepage (front matter only; all content comes from _data/)
blog.html             blog index page
```

## Publishing

```bash
cd ~/Documents/career/website
git add -A
git commit -m "Describe what changed"
git push
```

For troubleshooting, see [docs/deploy.md](docs/deploy.md).

## To do

- [x] Add the resume PDF (`assets/Yi_Wei_Resume.pdf`) and link it from `_data/bio.yml`
- [ ] Delete the sample post `_posts/2026-08-29-how-this-blog-works.md` and replace it with a real first post
- [ ] Fill in `_data/projects.yml` once the model-based RL / constrained search space work has results
- [ ] Add the website URL to the resume header
