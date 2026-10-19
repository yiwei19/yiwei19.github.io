# Service

**改这个文件：** `_data/service.yml`
**显示在：** 主页 Teaching 下面
**空的时候：** 整个板块自动隐藏

审稿、组织 workshop、志愿者之类的学术服务。最新的在前。

## 加一条

```yaml
- role: Reviewer
  venue: IEEE International Conference on Robotics and Automation (ICRA)
  year: "2027"
  detail: 可选，一句话补充。
```

| 字段 | 必填 | 说明 |
|---|---|---|
| `role` | 是 | 角色，比如 `Reviewer`、`Program Committee` |
| `venue` | 否 | 会议/期刊全称 |
| `year` | 否 | 加引号，右侧灰色显示 |
| `detail` | 否 | 小字补充说明 |

同一个角色给多个会议审稿，可以每个会议一条，也可以合成一条：
`venue: ICRA 2027, IROS 2026`，`year` 留空。
