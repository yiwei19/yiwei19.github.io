# Publications

**改这个文件：** `_data/publications.yml`
**显示在：** 主页 News 下面
**空的时候：** 整个板块自动隐藏

这是整个网站最重要的板块。每一条包含：左侧缩略图（视频或图），右侧标题、作者、
venue、这篇论文讲什么、**你的具体贡献**、链接、BibTeX。

## 加一篇

**加在文件最上面**（最新的在前）。整段复制下面的模板：

```yaml
- title: 论文标题（有冒号的话整句加引号）
  authors: First Author, Yi Wei, Third Author
  venue: arXiv preprint arXiv:XXXX.XXXXX
  year: 2027
  status: under review          # 可选，灰色斜体显示在 venue 后面
  image: /assets/paper2_teaser.png     # 或者用下面的 video，二选一
  media_caption: >                      # 可选，缩略图下面的小字说明
    图注一句话。
  summary: >
    这篇论文是关于什么的。问题是什么、你们怎么做的、结果有多好。
    三到五句，写给不在这个子领域的人看。
  contribution: >
    你在这篇论文里具体做了什么。二作三作尤其要写这一段。
  links:
    - label: arXiv
      url: https://arxiv.org/abs/XXXX.XXXXX
    - label: PDF
      url: https://arxiv.org/pdf/XXXX.XXXXX
    - label: code
      url: https://github.com/yiwei19/xxx
  bibtex: |
    @article{key2027,
      title   = {...},
      author  = {...},
      journal = {...},
      year    = {2027}
    }
```

## 字段

| 字段 | 必填 | 说明 |
|---|---|---|
| `title` | 是 | 会自动链到 `links` 里的**第一个**链接 |
| `authors` | 是 | 逗号分隔。**你的名字 `Yi Wei` 会自动加粗**，不用手动标 |
| `venue` | 是 | 会议/期刊名，或 `arXiv preprint arXiv:XXXX.XXXXX` |
| `year` | 否 | 显示在 venue 后面 |
| `status` | 否 | `under review` / `to appear` 之类，灰色斜体 |
| `image` | 否 | 静态缩略图，路径以 `/assets/` 开头 |
| `video` | 否 | 视频缩略图（自动播放、静音、循环）。和 `image` 二选一 |
| `poster` | 否 | 视频加载前显示的那一帧；视频放不出来时也用它兜底 |
| `media_caption` | 否 | 缩略图下面的小字 |
| `summary` | 否 | 论文讲什么 |
| `contribution` | 否 | 你的贡献，带左侧竖线显示 |
| `links` | 否 | `label` + `url` 的列表，按顺序显示 |
| `bibtex` | 否 | 用 `\|`（不是 `>`）开头，保留换行和缩进 |

**注意 `bibtex` 用 `|` 而不是 `>`** —— `>` 会把所有换行折成一行，BibTeX 就废了。

## 视频缩略图怎么做

放进 `assets/` 之前必须转码，**iPhone 和很多录屏工具默认导出 HEVC（H.265），
Chrome 和 Firefox 放不出来**，页面上会是黑框而且不报错：

```bash
ffmpeg -i 原视频.mp4 -an -vf "scale=1280:-2" \
  -c:v libx264 -profile:v high -pix_fmt yuv420p \
  -crf 26 -preset slow -movflags +faststart \
  ~/Documents/career/website/assets/新名字.mp4
```

`-an` 去掉音轨（缩略图是静音播放的，音轨纯属浪费体积）。转完确认一下：

```bash
ffprobe -v error -show_entries stream=codec_name,width,height \
  -of csv=p=0 assets/新名字.mp4
# 想看到 h264,1280,720 —— 如果是 hevc 就是没转成功
```

再截一帧当 poster：

```bash
ffmpeg -i assets/新名字.mp4 -ss 5 -frames:v 1 -q:v 4 assets/新名字_poster.jpg
```

然后在 YAML 里写：

```yaml
  video: /assets/新名字.mp4
  poster: /assets/新名字_poster.jpg
```

**GitHub 单文件硬上限 100 MB**，缩略图控制在 5 MB 以内比较合适。

## 论文被接收之后

改两个地方：

```yaml
  venue: Robotics: Science and Systems (RSS)   # 有冒号，记得整句加引号
  year: 2027
```

然后删掉 `status:` 那一行，再去 `_data/news.yml` 顶上加一条录取的 news。
