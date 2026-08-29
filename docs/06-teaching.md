# Teaching

**改这个文件：** `_data/teaching.yml`
**显示在：** 主页 Experience 下面
**空的时候：** 整个板块自动隐藏（现在就是空的）

助教、讲习班、指导过的低年级学生。

## 打开这个板块

把 `_data/teaching.yml` 里注释掉的模板取消注释：

```yaml
- role: Teaching Assistant
  course: CS 180 — Problem Solving and Object-Oriented Programming
  org: Purdue University
  period: Fall 2026
  detail: >
    可选。带了多少人、你额外做了什么（写了作业、开了复习课、做了自动评测）。
```

| 字段 | 必填 | 说明 |
|---|---|---|
| `course` | 是 | 课程号 + 课程名，粗体显示 |
| `role` | 是 | `Teaching Assistant` / `Grader` / `Instructor` |
| `org` | 否 | 学校 |
| `period` | 否 | `Fall 2026`，右对齐 |
| `detail` | 否 | 灰色小字 |

## 说明

助教经历对 PhD 申请是加分项，但**不要为了凑而凑**。一学期的 grader 写上去没问题，
写清楚就行 —— 夸大成 "co-instructor" 这种反而是减分。

同一门课带了多个学期，合并成一条，`period` 写 `Fall 2026, Spring 2027`。
