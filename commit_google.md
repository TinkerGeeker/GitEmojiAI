# Google Git 提交规范

## 核心规则

### 标题简洁
- 不超过 50 字符
- 动词开头（如 "Add"、"Fix"、"Update"、"Remove"）
- 首字母大写
- 不使用句号结尾

### 三段式结构
1. **标题**：简洁描述变更
2. **正文**：详细说明变更（可选）
3. **空行分隔**：标题和正文之间用空行分隔

### 原子提交原则
- 每个提交仅做一件事
- 避免混杂功能、修复和格式调整
- 便于审查、回滚和追踪问题

### 七条规则（基于 Chris Beams 的经典指南）

1. **用空行分隔标题和正文**：标题后空行，然后是正文。
2. **标题行限制为 50 个字符**：保持简洁可读。
3. **大写标题行**：首字母大写。
4. **标题行结尾不要加句号**：不需要标点。
5. **在标题行中使用祈使语气**：如 "Add"、"Fix"、"Update"。
6. **正文换行到 72 个字符**：便于阅读。
7. **使用正文解释什么和为什么**：专注于变更的原因，而不是如何实现。


## 提交类型

| 类型 | 说明 | 示例 |
|------|------|------|
| `Add` | 添加新功能 | `Add user authentication middleware` |
| `Fix` | 修复 Bug | `Fix login error handling` |
| `Update` | 更新现有功能 | `Update API documentation` |
| `Remove` | 删除功能 | `Remove deprecated feature` |
| `Refactor` | 重构代码 | `Refactor user authentication module` |
| `Optimize` | 性能优化 | `Optimize database queries` |
| `Test` | 测试相关 | `Add unit tests for user service` |
| `Docs` | 文档更新 | `Update installation guide` |
| `Build` | 构建系统变动 | `Update build configuration` |
| `Chore` | 其他维护任务 | `Update dependencies` |

## 示例

### 新功能
```
Add user authentication middleware

Implements JWT-based authentication for protected routes.
Adds middleware to verify JWT tokens.
Updates user session management.

Resolves #123
```

### Bug 修复
```
Fix login error handling

Fix null pointer exception in login process.
Add error logging for debugging.
Update user feedback messages.

Fixes #456
```

### 文档更新
```
Update API documentation

Add new endpoint documentation.
Update existing API examples.
Add authentication requirements section.
```

### 重构
```
Refactor user authentication module

Extract common authentication logic into separate functions.
Improve code readability and maintainability.
No functional changes.
```

### 性能优化
```
Optimize database queries

Add database indexes for frequently queried fields.
Optimize SQL queries to reduce execution time.
Improve response time by 40%.
```

## 最佳实践

- **标题要求**：简洁明了，不超过 50 字符
- **动词开头**：使用祈使语气
- **首字母大写**：标题首字母大写
- **无句号**：标题结尾不使用句号
- **详细说明**：解释为什么需要这个变更
- **提供背景**：相关背景信息
- **列出变更**：具体做了哪些改动
- **引用问题**：关联相关 Issue
- **原子提交**：每个提交只做一件事

## 常见错误

### 错误示例
```
# 错误：混合多个变更
Add user authentication and fix login bug and update documentation

# 错误：标题过长
Add user authentication feature with OAuth2 support and social media integration

# 错误：缺少空行
Add user authentication middleware
Implement authentication flow
```

### 正确示例
```
Add user authentication middleware

Implements JWT-based authentication for protected routes.
Adds middleware to verify JWT tokens.
Updates user session management.

Resolves #123