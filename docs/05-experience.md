# Experience —— 工作 / 研究经历

**改这个文件：** `_data/experience.yml`
**显示在：** 主页 Projects 下面
**空的时候：** 整个板块自动隐藏

放**你担任过的职位**：实验室研究岗、公司实习、正式工作。有职位名、机构、起止时间的，
都放这里。助教放 Teaching（[06-teaching.md](06-teaching.md)），不放这里。

## 加一条

**加在文件最上面**（最新的在前）。

```yaml
- role: Research Intern
  org: XYZ Robotics
  period: Summer 2027
  location: Sunnyvale, CA
  detail: >
    做了什么。一两句，写具体的东西，别写职责描述。
```

| 字段 | 必填 | 说明 |
|---|---|---|
| `role` | 是 | 职位名，粗体显示在左边 |
| `org` | 是 | 机构全称。第一次出现时把缩写写全 |
| `period` | 否 | 显示在同一行的最右边 |
| `location` | 否 | 跟在机构后面，用 ` · ` 分隔 |
| `detail` | 否 | 灰色小字，一到两句 |

## detail 怎么写

写**你做了什么、结果是什么**，不要写岗位职责。

不好：

> Responsible for robot perception and calibration tasks.

好：

> Built the eye-in-hand calibration pipeline for a Franka R3; diagnosed a ~30 mm
> frame-convention error and brought end-to-end execution to roughly 1 mm.

带数字的版本能被人记住，泛泛的那版不能。
