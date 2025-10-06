# Angular Git 提交规范

## 核心格式

```
<type>(<scope>): <subject>

<BLANK LINE>
<body>

<BLANK LINE>
<footer>
```

## 类型说明

| 类型 | 说明 | 示例 |
|------|------|------|
| `feat` | 新功能 | `feat(auth): add OAuth2 login support` |
| `fix` | Bug 修复 | `fix(api): handle null response` |
| `docs` | 文档更新 | `docs(readme): update installation guide` |
| `style` | 代码格式化 | `style(format): format code` |
| `refactor` | 重构 | `refactor(utils): optimize functions` |
| `perf` | 性能优化 | `perf(database): optimize queries` |
| `test` | 测试相关 | `test(unit): add unit tests` |
| `chore` | 构建工具变动 | `chore(deps): update dependencies` |
| `ci` | CI/CD 配置 | `ci(github): add workflow` |

## 核心规则

### 作用域（Scope）
可选，描述影响范围：
```
feat(auth): add OAuth2 login support
fix(api): handle null response
docs(readme): update installation guide
```

### 主题（Subject）
必填，简短描述：
- 不超过 50 字符
- 动词开头，首字母小写
- 简洁明了

### 破坏性变更
必须在脚注中声明：
```
feat(auth): add OAuth2 login support

Implement OAuth2 authentication.
Remove deprecated methods.

BREAKING CHANGE: Remove deprecated login API endpoints.
```

## 示例

### 新功能
```
feat(auth): add OAuth2 login support

Implement OAuth2 authentication flow.
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

## 最佳实践

- 提交信息要清晰明了
- 使用祈使语气（Add, Fix, Update等）
- 首字母大写
- 不要超过50字符的标题
- 必要时提供详细说明
- 每个提交只做一件事
- 破坏性变更必须在脚注中声明