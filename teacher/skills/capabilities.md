# capabilities.md — 教师能力档案

> **不参与每会话加载。** 仅在新老师注册时作为参考索引。
> 当课老师由 course_catalog.md 指定，直接通过 teacher/skills/{name}.skill.md 加载。
> 此文件只用于回答"系统中已有哪些老师可用"的查询。

---

## 注册教师列表

| name | display | type | source | tags |
|------|---------|------|--------|------|
| march | 三月 | fictional | built-in | socratic, analogy, ml |
| danheng | 丹恒 | fictional | built-in | socratic, precise, systematic |
| pamm | 帕姆 | fictional | built-in | peer-learner, companion |

---

## 注册流程（新老师）

1. 确认 `teacher/skills/{name}.skill.md` 存在
2. 在此表添加一行
3. 如果是 nuwa 创建 → 同时记录 `source: nuwa-distilled`
4. 通知系统："教师 {name} 已就绪"
