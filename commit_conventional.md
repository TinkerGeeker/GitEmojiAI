# Conventional Commits 规范

## 概述

Conventional Commits 规范是一个建立在提交消息之上的轻量级约定。它提供了一套简单的规则来创建明确的提交历史；这使得编写自动化工具变得更容易。这个约定与 SemVer 相结合，通过描述提交消息中的功能、修复和破坏性变更。

## 核心格式

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

提交包含以下结构元素，以向库的使用者传达意图：

- **fix:** 类型为 fix 的提交修补了代码库中的 bug（这与语义化版本控制中的 PATCH 相对应）。
- **feat:** 类型为 feat 的提交向代码库引入新功能（这与语义化版本控制中的 MINOR 相对应）。
- **BREAKING CHANGE:** 带有脚注 BREAKING CHANGE: 或在类型/作用域后附加 ! 的提交引入了破坏性 API 变更（与语义化版本控制中的 MAJOR 相对应）。BREAKING CHANGE 可以是任何类型的提交的一部分。
- 除 fix: 和 feat: 之外的其他类型是允许的，例如 [@commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/@commitlint/config-conventional)（基于 Angular 约定）推荐 build:、chore:、ci:、docs:、style:、refactor:、perf:、test: 等。
- BREAKING CHANGE: <description> 以外的脚注可以提供，并遵循类似于 git trailer 格式的约定。

除非它们包含 BREAKING CHANGE，否则其他类型的提交没有隐含的语义化版本控制效果。可以为提交的类型提供作用域，以提供额外的上下文信息，并包含在括号中，例如 feat(parser): 添加解析数组的能力。

## 类型说明

| 类型 | 说明 | 版本影响 | 示例 |
|------|------|----------|------|
| `feat` | 向代码库引入新功能 | MINOR 版本 | `feat: add OAuth2 login support` |
| `fix` | 修补代码库中的 bug | PATCH 版本 | `fix: handle null response` |
| `docs` | 仅文档变更 | 无版本影响 | `docs: update installation guide` |
| `style` | 代码格式化（不影响代码含义的变更） | 无版本影响 | `style: format code` |
| `refactor` | 既不修复 bug 也不添加功能的代码变更 | 无版本影响 | `refactor: optimize utility functions` |
| `perf` | 改进性能的代码变更 | PATCH 版本 | `perf: optimize database queries` |
| `test` | 添加缺失的测试或更正现有测试 | 无版本影响 | `test: add unit tests` |
| `build` | 影响构建系统或外部依赖的变更 | 无版本影响 | `build: update dependencies` |
| `ci` | 对 CI 配置文件和脚本的变更 | 无版本影响 | `ci: add GitHub workflow` |
| `chore` | 其他不修改 src 或测试文件的变更 | 无版本影响 | `chore: update package scripts` |

## 破坏性变更

### 在脚注中声明 BREAKING CHANGE
```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```

### 使用 ! 标识符突出破坏性变更
```
feat!: send an email to the customer when a product is shipped
```

### 带作用域的 ! 标识符
```
feat(api)!: send an email to the customer when a product is shipped
```

### 同时使用 ! 和 BREAKING CHANGE 脚注
```
chore!: drop support for Node 6

BREAKING CHANGE: use JavaScript features not available in Node 6.
```

## 示例

### 仅描述的提交消息
```
docs: correct spelling of CHANGELOG
```

### 带作用域的提交消息
```
feat(lang): add Polish language
```

### 带多段正文和多个脚注的提交消息
```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: #123
```

### 带描述和破坏性变更脚注的提交消息
```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```

### 带 ! 的提交消息突出破坏性变更
```
feat!: send an email to the customer when a product is shipped
```

### 带作用域和 ! 的提交消息突出破坏性变更
```
feat(api)!: send an email to the customer when a product is shipped
```

### 同时带 ! 和 BREAKING CHANGE 脚注的提交消息
```
chore!: drop support for Node 6

BREAKING CHANGE: use JavaScript features not available in Node 6.
```

## 语义化版本控制

Conventional Commits 规范与语义化版本控制 (SemVer) 相结合：

- **MAJOR 版本**：当有 BREAKING CHANGE 时
- **MINOR 版本**：当有新功能 (feat) 时
- **PATCH 版本**：当有 bug 修复 (fix) 或性能优化 (perf) 时

## 脚注格式

脚注遵循类似于 git trailer 的格式：

```
Footer-Key: Footer-Value
```

常见的脚注包括：
- `BREAKING CHANGE: <description>` - 破坏性变更说明
- `Fixes: #123` - 修复的问题
- `Closes: #456` - 关闭的问题
- `Reviewed-by: Name` - 审查者
- `Refs: #789` - 相关引用

## 最佳实践

- 提交信息要清晰明了
- 使用祈使语气（add, fix, update 等）
- 描述不应大写第一个字母
- 描述结尾没有句号
- 正文应解释变更的动机和影响
- 每个提交只做一件事
- 破坏性变更应明确标记
- 关联相关 issues 和 PR