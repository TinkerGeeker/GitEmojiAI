# Gitmoji 提交规范

## 核心格式

```
:emoji: 不超过 50 个字符的摘要，首字母大写，使用祈使语气，句末不要加句号

<BLANK LINE>
提交信息主体

<BLANK LINE>
引用相关 issue 或 PR 编号 <#123>
```
## Emoji 类型说明

| Emoji | Emoji 代码 | 说明 | 示例 |
|-------|-----------|------|------|
| ✨ | `:sparkles:` | 新功能 | `:sparkles: Add user authentication` |
| 🐛 | `:bug:` | Bug 修复 | `:bug: Fix login error` |
| 📝 | `:memo:` | 文档更新/撰写文档 | `:memo: Update README` |
| 🎨 | `:art:` | 代码格式化/改进代码结构 | `:art: Format code` |
| 🔧 | `:wrench:` | 配置文件修改 | `:wrench: Update config` |
| 🚀 | `:rocket:` | 部署功能/发布版本 | `:rocket: Deploy to production` |
| 💄 | `:lipstick:` | UI/样式更新 | `:lipstick: Update login page` |
| 📦 | `:package:` | 添加依赖 | `:package: Add lodash dependency` |
| 🚧 | `:construction:` | 工作进行中 | `:construction: Work in progress` |
| 🔄 | `:recycle:` | 重构 | `:recycle: Refactor user service` |
| ⚡ | `:zap:` | 性能优化 | `:zap: Optimize database queries` |
| 🔥 | `:fire:` | 移除代码 | `:fire: Remove deprecated code` |
| 🎉 | `:tada:` | 初次提交 | `:tada: Initialize Repo` |
| 🚑 | `:ambulance:` | 重要补丁 | `:ambulance: Critical security patch` |
| 🔒 | `:lock:` | 修复安全问题 | `:lock: Fix security vulnerability` |
| 💚 | `:green_heart:` | 修复 CI 构建 | `:green_heart: Fix CI build` |
| 🚨 | `:rotating_light:` | 修复警告/移除 linter 警告 | `:rotating_light: Fix linter warnings` |
| 🎯 | `:dart:` | 修复问题 | `:dart: Fix specific issue` |
| 🆕 | `:new:` | 引入新功能 | `:new: Introduce new feature` |
| 📖 | `:book:` | 撰写文档 | `:book: Write documentation` |
| 📚 | `:books:` | 添加文档 | `:books: Add documentation` |
| ➕ | `:heavy_plus_sign:` | 增加一个依赖 | `:heavy_plus_sign: Add dependency` |
| ⬆️ | `:arrow_up:` | 升级依赖 | `:arrow_up: Upgrade dependency` |
| ➖ | `:heavy_minus_sign:` | 减少一个依赖 | `:heavy_minus_sign: Remove dependency` |
| ⬇️ | `:arrow_down:` | 降级依赖 | `:arrow_down: Downgrade dependency` |
| 👷 | `:construction_worker:` | 添加 CI 构建系统 | `:construction_worker: Add CI build system` |
| 🧪 | `:test_tube:` | 添加测试 | `:test_tube: Add unit tests` |
| ✅ | `:white_check_mark:` | 增加测试 | `:white_check_mark: Add tests` |
| 🤖 | `:robot_face:` | 添加自动化 | `:robot_face: Add automation` |
| 📈 | `:chart_with_upwards_trend:` | 添加分析/跟踪代码 | `:chart_with_upwards_trend: Add analytics` |
| 🔨 | `:hammer:` | 开发脚本 | `:hammer: Add development script` |
| 🌐 | `:globe_with_meridians:` | 国际化 | `:globe_with_meridians: Add i18n support` |
| ♿ | `:wheelchair:` | 可访问性 | `:wheelchair: Improve accessibility` |
| 📌 | `:pushpin:` | 固定版本 | `:pushpin: Lock dependency version` |
| 🔍 | `:mag:` | 改善 SEO | `:mag: Improve SEO` |
| 🗑 | `:wastebasket:` | 删除文件 | `:wastebasket: Delete unused file` |
| 🔐 | `:closed_lock_with_key:` | 添加密钥 | `:closed_lock_with_key: Add API key` |
| 📋 | `:clipboard:` | 列表更新 | `:clipboard: Update todo list` |
| 🔀 | `:twisted_rightwards_arrows:` | 分支合并 | `:twisted_rightwards_arrows: Merge branch` |
| 🔖 | `:bookmark:` | 发行/版本标签 | `:bookmark: Release tag` |
| 🎬 | `:clapper:` | 更新演示/示例 | `:clapper: Update demo` |
| 🐧 | `:penguin:` | Linux 相关 | `:penguin: Fix Linux build` |
| 🍎 | `:apple:` | macOS 相关 | `:apple: Fix macOS issue` |
| 🪟 | `:window:` | Windows 相关 | `:window: Fix Windows build` |
| 🐳 | `:whale:` | Docker 相关 | `:whale: Update Dockerfile` |
| 🐎 | `:racehorse:` | 加速应用 | `:racehorse: Speed up application` |

## 示例

### 新功能
```
✨ Add user authentication

Implement JWT-based authentication for protected routes.
Add login and logout functionality.
Update user session management.

Closes #123
```

### Bug 修复
```
🐛 Fix login error handling

Fix null pointer exception in login process.
Add error logging for debugging.
Update user feedback messages.

Fixes #456
```

### 文档更新
```
📝 Update API documentation

Add new endpoint documentation.
Update existing API examples.
Add authentication requirements section.

Related to #789
```

### 性能优化
```
⚡ Optimize database queries

Add database indexes for frequently queried fields.
Optimize SQL queries to reduce execution time.
Improve response time by 40%.

Closes #101
```

### 重构
```
🔄 Refactor user service

Extract common user logic into separate functions.
Improve code readability and maintainability.
No functional changes.

Related to #202
```

## 最佳实践

### 核心规则
- **标题简洁**：不超过 50 字符
- **动词开头**：使用祈使语气（Add、Fix、Update、Remove等）
- **首字母大写**：标题首字母大写
- **无句号**：标题结尾不使用句号
- **详细说明**：解释为什么需要这个变更
- **提供背景**：相关背景信息
- **列出变更**：具体做了哪些改动
- **引用问题**：关联相关 Issue

### 原子提交原则
- 每个提交仅做一件事
- 避免混杂功能、修复和格式调整
- 便于审查、回滚和追踪问题

### Emoji 选择指南
- **功能开发**：使用 ✨ `:sparkles:`
- **Bug 修复**：使用 🐛 `:bug:`
- **文档更新**：使用 📝 `:memo:`
- **性能优化**：使用 ⚡ `:zap:`
- **重构**：使用 🔄 `:recycle:`
- **配置修改**：使用 🔧 `:wrench:`
- **部署发布**：使用 🚀 `:rocket:`
- **安全修复**：使用 🔒 `:lock:`

## 参考

- [gitmoji](https://github.com/carloscuesta/gitmoji) - Gitmoji 官方仓库
- [git-commit-emoji-cn](https://github.com/liuchengxu/git-commit-emoji-cn) - Git 提交表情符号中文指南
- [emoji-cheat-sheet](https://github.com/ikatyang/emoji-cheat-sheet) - Emoji 速查表