# nuwa-integration.md — 新教师创建桥接

> 本文件在"当课老师不存在"时加载。
> 流程：course_catalog 指定老师 → teacher/skills/{name}.skill.md 不存在
>   → 检查 capabilities.md → 也不存在
>   → 执行本桥接流程创建新老师

---

## 触发条件

当 `teacher/skills/{teacher_name}.skill.md` 不存在，且 `teacher/skills/capabilities.md` 中也没有该教师时：

```
1. 确认 teacher_name（从 course_catalog.md 或 learner_profile.md 获取）
2. 确认教学科目和风格（从 course_catalog.md 的课程描述获取）
3. 确认是否需要真实人物蒸馏或虚构创作
```

## 调用 nuwa-skill

nuwa 安装在 `.claude/skills/nuwa/` 目录。

**调用方式**（选择适合场景的一种）：

### A) 蒸馏真实人物

当需要将某位真实专家（如某个学科领域的知名人物）转化为老师时：

```
Skill("huashu-nuwa", args="蒸馏 {人物名}，作为 LearningMultiverse 的 {科目} 老师。
要求输出为 teacher/skills/{name}.skill.md 格式。")
```

### B) 虚构创作新老师

当需要为课程创作一个全新的虚构老师时：

```
Skill("huashu-nuwa", args="为 LearningMultiverse 课程 {课程名} 创建一个虚构老师，
名叫 {name}，教学风格 {风格描述}，教授科目 {科目}。
要求输出为 teacher/skills/{name}.skill.md 格式。")
```

## 输出转换

nuwa-skill 生成的 SKILL.md 格式可能与 `teacher/skills/` 格式略有不同。
创建后**必需**调整以下字段：

1. **frontmatter**：确保包含 `type: teacher`、`source: nuwa-distilled`、`capabilities:`
2. **config**：添加 `partner:`（轮值搭档，可选）、`chapter_pattern:`（授课规律）
3. **保存路径**：必须是 `teacher/skills/{name}.skill.md`

## 注册

创建完成后，在 `teacher/skills/capabilities.md` 的注册表中添加一行：

```
| {name} | {显示名} | fictional | nuwa-distilled | {tags} |
```

## 首次使用

新老师注册后：
1. 本会话直接加载新创建的 skill 文件
2. 通知用户"教师 {name} 已就绪"
3. 后续会话自动走正常加载路径
