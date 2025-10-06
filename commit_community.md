# Git 提交规范 - 社区扩展与最佳实践

## 行业特定类型

### C++ 项目
| 类型 | 说明 | 示例 |
|------|------|------|
| `security` | 安全相关 | `security: fix buffer overflow vulnerability` |
| `memory` | 内存管理 | `memory: fix memory leak in user service` |
| `performance` | 性能优化 | `performance: optimize memory allocation` |
| `concurrency` | 并发处理 | `concurrency: fix race condition in thread pool` |

### 前端项目
| 类型 | 说明 | 示例 |
|------|------|------|
| `i18n` | 国际化 | `i18n: add Chinese language support` |
| `a11y` | 无障碍访问 | `a11y: improve screen reader support` |
| `ui` | 用户界面 | `ui: update login page design` |
| `ux` | 用户体验 | `ux: improve form validation feedback` |
| `responsive` | 响应式设计 | `responsive: add mobile layout support` |

### 后端项目
| 类型 | 说明 | 示例 |
|------|------|------|
| `api` | API 变更 | `api: add new user endpoint` |
| `db` | 数据库变更 | `db: add user preferences table` |
| `cache` | 缓存优化 | `cache: implement Redis caching` |
| `auth` | 认证授权 | `auth: implement OAuth2 authentication` |

### AI/ML 项目
| 类型 | 说明 | 示例 |
|------|------|------|
| `model` | 模型变更 | `model: update sentiment analysis model` |
| `dataset` | 数据集变更 | `dataset: add new training data` |
| `training` | 训练过程 | `training: optimize hyperparameters` |
| `inference` | 推理优化 | `inference: optimize model inference speed` |

### 移动端项目
| 类型 | 说明 | 示例 |
|------|------|------|
| `ios` | iOS 相关 | `ios: fix crash on iOS 15` |
| `android` | Android 相关 | `android: fix memory leak in Android` |
| `cross-platform` | 跨平台 | `cross-platform: add Windows support` |
| `performance` | 性能优化 | `performance: optimize app startup time` |

## Emoji 扩展

| Emoji | 类型 | 说明 |
|-------|------|------|
| ✨ | `feat` | 新功能 |
| 🐛 | `fix` | Bug 修复 |
| 📝 | `docs` | 文档更新 |
| 🎨 | `style` | 代码格式化 |
| 🔧 | `refactor` | 重构 |
| ⚡ | `perf` | 性能优化 |
| 🧪 | `test` | 测试相关 |
| 🏗️ | `build` | 构建系统变动 |
| 🤖 | `ci` | CI/CD 配置 |
| 🧹 | `chore` | 其他维护任务 |
| 🔒 | `security` | 安全相关 |
| 💾 | `memory` | 内存管理 |
| 🌐 | `i18n` | 国际化 |
| ♿ | `a11y` | 无障碍访问 |
| 📱 | `ui` | 用户界面 |
| 🎯 | `ux` | 用户体验 |
| 🔄 | `api` | API 变更 |
| 🗄️ | `db` | 数据库变更 |
| ⚡ | `cache` | 缓存优化 |
| 📊 | `model` | 模型变更 |
| 📈 | `performance` | 性能优化 |
| 🔥 | `hotfix` | 紧急修复 |

## 分支命名建议

### 功能分支
```
feature/描述性名称
feature/user-authentication
feature/payment-gateway
feature/dashboard-analytics
```

### Bug 分支
```
fix/问题描述
fix/login-error
fix/api-timeout
fix/memory-leak
```

### 热修复分支
```
hotfix/问题描述
hotfix/security-patch
hotfix/critical-bug
```

### 发布分支
```
release/版本号
release/v1.0.0
release/v2.1.0
```

## 原子提交原则

### 核心概念
- **单一职责**：每个提交只包含单一逻辑变更
- **独立可理解**：每个提交都能独立理解
- **可回滚性**：可以安全地回滚单个提交
- **可审查性**：便于代码审查和讨论

### 提交信息模板

#### 功能开发模板
```
✨ feat: add [功能名称]

- 实现核心功能
- 添加相关测试
- 更新文档
- 关联 Issue: #123
```

#### Bug 修复模板
```
🐛 fix: fix [问题描述]

- 修复具体问题
- 添加错误处理
- 添加相关测试
- 关联 Issue: #456
```

#### 文档更新模板
```
📝 docs: update [文档名称]

- 更新文档内容
- 添加新章节
- 修正错误信息
- 更新示例代码
```

#### 重构模板
```
🔧 refactor: refactor [模块名称]

- 提取公共逻辑
- 改进代码结构
- 优化性能
- 保持功能不变
```

## 最佳实践

### 提交信息规范
- **长度控制**：不超过 50 字符
- **动词开头**：使用祈使语气
- **首字母大写**：标题首字母大写
- **无句号**：标题结尾不使用句号
- **详细说明**：解释为什么需要这个变更
- **提供背景**：相关背景信息
- **列出变更**：具体做了哪些改动
- **引用问题**：关联相关 Issue
