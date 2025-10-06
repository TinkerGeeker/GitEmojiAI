# Conventional Commits 规范

## 核心格式

```
<type>(<scope>): <subject>

<BLANK LINE>
<body>

<BLANK LINE>
<footer>
```

## 类型说明

| 类型 | 说明 | 版本影响 | 示例 |
|------|------|----------|------|
| `feat` | 新功能 | MINOR 版本 | `feat(auth): add OAuth2 login support` |
| `fix` | Bug 修复 | PATCH 版本 | `fix(api): handle null response` |
| `docs` | 文档更新 | 无版本影响 | `docs(readme): update installation guide` |
| `style` | 代码格式化 | 无版本影响 | `style(format): format code` |
| `refactor` | 重构 | 无版本影响 | `refactor(utils): optimize functions` |
| `perf` | 性能优化 | PATCH 版本 | `perf(database): optimize queries` |
| `test` | 测试相关 | 无版本影响 | `test(unit): add unit tests` |
| `build` | 构建系统变动 | 无版本影响 | `build(deps): update dependencies` |
| `ci` | CI/CD 配置 | 无版本影响 | `ci(github): add workflow` |
| `chore` | 其他维护任务 | 无版本影响 | `chore(config): update rules` |

## 破坏性变更

### 方式一：在脚注中声明
```
feat(auth): add OAuth2 login support

Implement OAuth2 authentication flow.
Remove deprecated login methods.

BREAKING CHANGE: Remove deprecated login API endpoints.
```

### 方式二：使用 `!` 标识符
```
feat(auth)!: remove legacy API

Remove deprecated authentication methods.
Update all references to use new API.
```

## 示例

### 新功能
```
feat(auth): add OAuth2 login support

Implement OAuth2 authentication flow with Google and GitHub providers.
Add login button and callback handling.
Update user session management.

BREAKING CHANGE: Remove deprecated login API endpoints.
```

### Bug 修复
```
fix(api): handle null response in user endpoint

Fix null pointer exception when user data is not available.
Add null checks and default values.
Update error handling logic.

Fixes #456
```

### 文档更新
```
docs(readme): update installation guide

Add new installation steps for Windows users.
Update dependency versions.
Add troubleshooting section.
```

### 重构
```
refactor(utils): optimize utility functions

Extract common validation logic into separate functions.
Improve code readability and maintainability.
No functional changes.
```

### 性能优化
```
perf(database): optimize query performance

Add database indexes for frequently queried fields.
Optimize SQL queries to reduce execution time.
Improve response time by 40%.
```

## 语义化版本控制

- **MAJOR 版本**：不兼容的 API 修改（包含 BREAKING CHANGE）
- **MINOR 版本**：向下兼容的功能性新增
- **PATCH 版本**：向下兼容的问题修正

## 最佳实践

- 提交信息要清晰明了
- 使用祈使语气（Add, Fix, Update等）
- 首字母大写
- 不要超过50字符的标题
- 必要时提供详细说明
- 每个提交只做一件事
- 破坏性变更必须在脚注中声明或使用 `!` 标识符
- 关联相关 Issue（如 Fixes #123）