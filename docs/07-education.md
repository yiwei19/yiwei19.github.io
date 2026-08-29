# Education

**改这个文件：** `_data/education.yml`
**显示在：** 主页 Teaching 下面
**空的时候：** 整个板块自动隐藏

## 加一条

**最新的在最上面。**

```yaml
- school: Purdue University
  degree: B.S. in Computer Science and Mathematics
  period: expected 2028
  location: West Lafayette, IN
  detail: Minor in Electrical Engineering Technology.
```

| 字段 | 必填 | 说明 |
|---|---|---|
| `school` | 是 | 学校全名，粗体 |
| `degree` | 否 | 学位和专业。交换/访学写 `Exchange semester` |
| `period` | 否 | `2024–2028`、`expected 2028`，右对齐 |
| `location` | 否 | 城市，跟在学位后面 |
| `detail` | 否 | 灰色小字：辅修、GPA、荣誉项目 |

**不填的字段整行删掉就行**，留空（`degree: ""`）也不会显示多余的分隔符。

## 要不要写 GPA

自己决定。经验法则：**3.9 以上写，不到就不写** —— 空着没人会追问，写一个中等的数字
反而把注意力从研究上引开了。要写就放 `detail`：

```yaml
  detail: GPA 3.94/4.00. Minor in Electrical Engineering Technology.
```

## 交换和转学

单独列一条就行，`degree` 写 `Exchange semester` 或 `Visiting student`，
`period` 写学期。转学的话两所学校都列，招生老师看得懂时间线。
