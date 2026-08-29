# Yi Wei — Personal Website

单文件学术主页（参考 tairanhe.com 风格），无框架、无构建步骤。
线上地址（部署后）：https://yiwei19.github.io

## 需要你放入的文件（assets/ 文件夹）

| 文件 | 用途 | 状态 |
|---|---|---|
| `assets/profile.jpg` | 头像（方形裁剪最佳） | 待补 |
| `assets/Yi_Wei_CV.pdf` | 简历 PDF（导出英文版即可） | 待补 |
| `assets/meanflow_teaser.png` | 论文 teaser 图（从 arXiv 论文里截 Fig.1） | 待补 |
| `assets/franka_grasp_demo.mp4` | Franka 抓取 demo 视频（压缩到 <20MB：`ffmpeg -i in.mp4 -vf scale=-2:576 -crf 28 out.mp4`） | 待补，且需先跟导师确认可公开 |

文件缺失时页面显示灰色占位块，不会报错——可以先上线再逐步补素材。

## 页面结构

Header（头像 + bio）→ News → **Publications** → Research & Projects → Earlier Projects → Experience

- Publications：目前一篇，*Fast Generative Grasping via Lie Group-Constrained MeanFlow*（arXiv:2608.26076，你是二作），带 arXiv / PDF / BibTeX 链接。
- Projects：Franka R3 real-robot deployment（论文的硬件部分，写你的具体贡献）。
- index.html 里有一段注释掉的 project 模板，加新项目时复制那段填内容即可。

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
- [ ] model-based RL / 约束搜索空间（TD-MPC 方向）项目有初步结果后加进 Projects
- [ ] 简历页眉加一行网站地址
- [ ] 考虑加 Google Scholar 链接（有 profile 之后）
