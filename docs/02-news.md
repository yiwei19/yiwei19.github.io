# News

**改这个文件：** `_data/news.yml`
**显示在：** 主页 Bio 下面
**空的时候：** 整个板块自动隐藏

News 是招生老师最先扫的一块。放**发生了的事**（论文上线、被接收、开始某个岗位、
拿了什么奖），不要放计划。

## 加一条

**加在文件最上面** —— 最新的在最前面，页面按文件顺序显示，不会自动排序。

```yaml
- date: "10/2026"
  text: >
    这里写发生了什么。可以带 <a href="https://...">链接</a> 和 <i>斜体的论文标题</i>。
```

| 字段 | 必填 | 说明 |
|---|---|---|
| `date` | 是 | **必须加引号**，否则 `08/2026` 会被 YAML 当成数字算式。写 `"08/2026"` 或 `"2026"` 都行 |
| `text` | 是 | 一句话。可以写 HTML |

## 例子

```yaml
- date: "12/2026"
  text: >
    <i>Fast Generative Grasping via Lie Group-Constrained MeanFlow</i> 被
    <a href="https://roboticsconference.org">RSS 2027</a> 接收。

- date: "10/2026"
  text: Started as a research intern at XYZ Robotics.
```

## 保持多长

**6 到 8 条封顶。** 超过就把最老的删掉 —— News 是"最近在发生什么"，不是履历，
履历有 Experience 和 Education 两个板块。
