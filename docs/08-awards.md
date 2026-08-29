# Awards & Honors

**改这个文件：** `_data/awards.yml`
**显示在：** 主页最后一个板块
**空的时候：** 整个板块自动隐藏（现在就是空的）

## 打开这个板块

把 `_data/awards.yml` 里注释掉的模板取消注释：

```yaml
- title: Dean's List
  org: Purdue University College of Science
  year: "2026"
  detail: >
    可选。竞争程度、入选比例、覆盖范围 —— 外校的人不知道这个奖有多难拿。
```

| 字段 | 必填 | 说明 |
|---|---|---|
| `title` | 是 | 奖项名，粗体 |
| `year` | 否 | **加引号**：`"2026"`。右对齐 |
| `org` | 否 | 颁奖机构 |
| `detail` | 否 | 灰色小字 |

**最新的在最上面。**

## detail 值得写

`Outstanding Undergraduate Research Award` 单看不知道分量。加一句就完全不同：

```yaml
- title: Outstanding Undergraduate Research Award
  org: Purdue University Department of Computer Science
  year: "2027"
  detail: One of three awarded across roughly 900 CS undergraduates.
```

## 要不要放奖学金金额

不要。写奖学金的**名字**和**选拔性**，不写金额 —— 金额属于财务信息，
放在公开主页上没有好处。
