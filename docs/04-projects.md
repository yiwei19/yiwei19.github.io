# Projects

**改这个文件：** `_data/projects.yml`
**显示在：** 主页 Publications 下面
**空的时候：** 整个板块自动隐藏（现在就是空的）

放**还没成论文**的研究和工程项目。已经有论文的工作放 Publications，不要两边都放
—— 重复会让人觉得成果比实际多。

## 打开这个板块

`_data/projects.yml` 里已经有一段注释掉的模板，把每行开头的 `#` 和一个空格删掉，
填上内容，板块就出现了。

```yaml
- title: Constrained Search Spaces for Model-Based RL
  org: Purdue CoMMA Lab
  period: 2026–present
  status: in progress
  summary: >
    这个项目在做什么，为什么值得做。
  contribution: >
    可选。你在里面具体负责什么 —— 单人项目就不用写了。
  tags: TD-MPC2 · model-based RL · meta-learning
  links:
    - label: code
      url: https://github.com/yiwei19/xxx
```

## 字段

| 字段 | 必填 | 说明 |
|---|---|---|
| `title` | 是 | 项目名 |
| `org` | 否 | 实验室或公司 |
| `period` | 否 | `2026–present`、`Summer 2027` |
| `status` | 否 | `in progress` 之类，灰色斜体 |
| `image` | 否 | 缩略图，`/assets/` 开头 |
| `media_caption` | 否 | 缩略图下的小字 |
| `summary` | 否 | 项目讲什么 |
| `contribution` | 否 | 你的贡献，带左侧竖线 |
| `tags` | 否 | 一行关键词，用 ` · ` 分隔 |
| `links` | 否 | `label` + `url` 列表 |

## 什么该放这里

- 你**主导**的、还在做的研究方向
- 有实际产出（能跑的系统、能看的 demo）的工程项目
- 课程项目 —— 但只放最好的一两个，而且要写清楚是课程项目

## 什么不该放

- **复现别人的工作**，除非你在描述里明确写了 "reproduced" / "ported"。
  招生老师和审稿人对这件事很敏感，措辞含糊比不放更伤。
- 只写了个开头的东西。宁可少放。
