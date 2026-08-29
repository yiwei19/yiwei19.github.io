# Yi Wei — Personal Website

线上地址：https://yiwei19.github.io

## 需要你放入的文件（assets/ 文件夹）

| 文件 | 用途 | 状态 |
|---|---|---|
| `assets/profile.jpg` | 头像（方形裁剪最佳） | 待补 |
| `assets/Yi_Wei_CV.pdf` | 简历 PDF（导出英文版即可） | 待补 |
| `assets/meanflow_teaser.png` | 论文 teaser 图（从 arXiv 论文里截 Fig.1），demo 视频缺失时的备用缩略图 | 待补 |
| `assets/franka_grasp_demo.mp4` | Franka 抓取 demo 视频，**用作论文条目的缩略图**（压缩到 <20MB：`ffmpeg -i in.mp4 -vf scale=-2:576 -crf 28 out.mp4`） | 待补，且需先跟导师确认可公开 |

文件缺失时页面显示灰色占位块，不会报错——可以先上线再逐步补素材。

## 页面结构

Header（头像 + bio）→ News → **Publications** → Experience

纯 publication-centric 学术主页（参考 tairanhe.com / jonbarron.info 的做法）：不单列 project 区块，
所有工作通过论文条目呈现。每条论文的格式是：

1. 左侧缩略图（优先用 demo 视频 `franka_grasp_demo.mp4`，没有就自动退回 teaser 图，再没有就显示灰色占位块）
2. 标题（链到 arXiv）→ 作者列表（你的名字加粗）→ venue
3. 第一段：这篇论文是关于什么的
4. 第二段（带左侧竖线）：**My contribution** —— 你在其中的具体工程贡献
5. arXiv / PDF 链接 + 可折叠 BibTeX

index.html 里有一段注释掉的 `.pub` 模板，加第二篇论文时复制那段填内容即可。

## 部署到 GitHub Pages

1. 在 GitHub 新建**空**仓库，名字必须是 `yiwei19.github.io`（不要勾选 add README）
2. 在本文件夹里（git 已初始化并 commit 好）：
   ```bash
   cd ~/Documents/career/website
   git push -u origin main
   ```
3. 等 1–2 分钟，访问 https://yiwei19.github.io

## 待办

- [ ] 补 assets/ 里的四个文件
- [ ] 确认 demo 视频/方法细节的公开范围（先问导师）
- [ ] 论文被会议接收后，把 Publications 里的 "arXiv preprint" 改成会议名
- [ ] model-based RL / 约束搜索空间（TD-MPC 方向）出论文后，用 index.html 里的 .pub 模板加第二条
- [ ] 简历页眉加一行网站地址
- [ ] 考虑加 Google Scholar 链接（有 profile 之后）
