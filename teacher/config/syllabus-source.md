# syllabus-source.md — 教材来源索引

> 本文件记录每门课程的教材来源信息。
> 新增课程时，由启动流程（第零步 D）引导用户选择来源并记录于此。
> 文件存储在 `Docs/{course_id}/` 目录下。

---

## 来源类型说明

| 类型 | code | 说明 | 存储位置 |
|------|------|------|---------|
| 本地文件 | `local` | 用户指定本地路径，复制到项目 | `Docs/{course_id}/` |
| 网址 | `url` | 从 URL 下载或提取内容 | `Docs/{course_id}/` |
| 搜索推荐 | `search` | 自动搜索推荐，选中后按 local/url 处理 | `Docs/{course_id}/` |

---

## 课程教材来源

| 课程 ID | 来源类型 | 原始路径/URL | 本地副本路径 | 备注 |
|---------|---------|-------------|-------------|------|
| ml-yearning | local | `materials/textbook/andrew-ng-machine-learning-yearning.pdf` | `Docs/andrew-ng-machine-learning-yearning.pdf` | 本地教材 |
| kaggle-agent | local | `Docs/Kaggle/` (多文件) | `Docs/Kaggle/` | 本地教材合集 |
| agent-tools-interoperability | local | `Docs/Kaggle/Agent Tools & Interoperability_Day_2.pdf` | `Docs/Kaggle/` | 本地教材 |
| agent-skills | local | `Docs/Kaggle/Agent Skills_Day_3.pdf` | `Docs/Kaggle/` | 本地教材 |

---

## 新增课程教材来源记录

```markdown
| {course_id} | {local/url/search} | {原始路径或URL} | {副本路径} | {备注} |
```

## 教材文件管理规则

1. **本地文件**：复制到 `Docs/{course_id}/`，保留原始扩展名
2. **URL 文件**：
   - 可下载格式（PDF、epub 等）→ `curl -o Docs/{course_id}/{filename}`
   - 网页内容 → `WebFetch` 提取后保存为 `Docs/{course_id}/content.md`
   - 同时生成 `Docs/{course_id}/source.txt` 记录原始 URL
3. **搜索推荐**：
   - 搜索后展示 3-5 个候选
   - 用户选定后，按 local 或 url 流程处理
   - 如果用户选的是推荐教材的在线版本 → url 流程
   - 如果用户提供本地下载的版本 → local 流程
