# Angular Git 提交规范

## 概述

我们对 Git 提交消息的格式有非常精确的规定。这种格式有助于更容易阅读提交历史，并使其可用于变更日志生成。

每个提交消息由标题、正文和脚注组成。

```
<header>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

标题是强制性的，必须符合提交消息标题格式。

正文对除 "docs" 类型外的所有提交都是强制性的。当正文存在时，它必须至少 20 个字符长，并必须符合提交消息正文格式。

脚注是可选的。提交消息脚注格式描述了脚注的用途及其必须具有的结构。

## 提交消息标题

```
<type>(<scope>): <short summary>
  │       │             │
  │       │             └─⫸ 摘要使用现在时。不大写。没有句末句号。
  │       │
  │       └─⫸ 提交作用域：animations|bazel|benchpress|common|compiler|compiler-cli|core|
  │                          elements|forms|http|language-service|localize|platform-browser|
  │                          platform-browser-dynamic|platform-server|router|service-worker|
  │                          upgrade|zone.js|packaging|changelog|docs-infra|migrations|
  │                          devtools
  │
  └─⫸ 提交类型：build|ci|docs|feat|fix|perf|refactor|test
```

`<type>` 和 `<summary>` 字段是强制性的，`(<scope>)` 字段是可选的。

### 类型

必须是以下之一：

| 类型 | 说明 |
|------|------|
| `build` | 影响构建系统或外部依赖的变更（示例作用域：gulp, broccoli, npm） |
| `ci` | 对 CI 配置文件和脚本的变更（示例：Github Actions, SauceLabs） |
| `docs` | 仅文档变更 |
| `feat` | 新功能 |
| `fix` | Bug 修复 |
| `perf` | 改进性能的代码变更 |
| `refactor` | 既不修复 bug 也不添加功能的代码变更 |
| `test` | 添加缺失的测试或更正现有测试 |

### 作用域

作用域应该是受影响的 npm 包的名称（由阅读从提交消息生成的变更日志的人感知）。

以下是支持的作用域列表：

- animations
- bazel
- benchpress
- changelog
- common
- compiler
- compiler-cli
- core
- dev-infra
- devtools
- docs-infra
- elements
- forms
- http
- language-service
- localize
- migrations
- packaging
- platform-browser
- platform-browser-dynamic
- platform-server
- router
- service-worker
- upgrade
- zone.js

"使用包名称" 规则目前有几个例外：

- `packaging`：用于更改我们所有包中的 npm 包布局的变更，例如公共路径变更、对所有包进行的 package.json 变更、d.ts 文件/格式变更、对捆绑包的变更等。

- `changelog`：用于更新 CHANGELOG.md 中的发布说明

- `dev-infra`：用于 /scripts 和 /tools 目录内的与 dev-infra 相关的变更

- `docs-infra`：用于 /adev 目录内对 docs-app (angular.dev) 的基础设施变更，例如应用程序代码、工具或配置。对于文档内容的修改（例如，编辑 .md 文件），请改用不带作用域的 `docs:`。

- `migrations`：用于对 ng update 迁移的变更。

- `devtools`：用于浏览器扩展中的变更。

- `none/empty string`：适用于跨所有包进行的测试和重构变更（例如 `test: add missing unit tests`）以及与特定包无关的文档变更（例如 `docs: fix typo in tutorial`）。

### 摘要

使用摘要字段提供变更的简洁描述：

- 使用祈使语气、现在时："change" 而不是 "changed" 或 "changes"
- 不要大写第一个字母
- 结尾没有句号 (.)

## 提交消息正文

正如摘要一样，使用祈使语气、现在时："fix" 而不是 "fixed" 或 "fixes"。

在提交消息正文中解释变更的动机。这个提交消息应该解释为什么进行这个变更。您可以包括对之前行为与新行为的比较，以说明变更的影响。

## 提交消息脚注

脚注可以包含关于破坏性变更和弃用以及引用 GitHub issues 和其他 PR 的信息，这些 PR 被此提交关闭或与之相关。例如：

```
BREAKING CHANGE: <breaking change summary>
<BLANK LINE>
<breaking change description + migration instructions>
<BLANK LINE>
<BLANK LINE>
Fixes #<issue number>
```

或

```
DEPRECATED: <what is deprecated>
<BLANK LINE>
<deprecation description + recommended update path>
<BLANK LINE>
<BLANK LINE>
Closes #<pr number>
```

破坏性变更部分应该以短语 "BREAKING CHANGE:" 开头，后跟破坏性变更的简要摘要、空行，以及包含迁移说明的破坏性变更的详细描述。

同样，弃用部分应该以 "DEPRECATED:" 开头，后跟简短描述弃用了什么、空行，以及包含推荐更新路径的弃用的详细描述。

## 回滚提交

如果提交回滚了之前的提交，它应该以 `revert:` 开头，后跟被回滚提交的标题。

提交消息正文的内容应该包含：

- 以以下格式提供被回滚提交的 SHA 的信息：`This reverts commit <SHA>`，
- 回滚提交消息的清晰描述。

## 示例

### 新功能
```
feat(auth): add OAuth2 login support

Implement OAuth2 authentication flow for user login.
Add login button and callback handling to the UI.
Update user session management to handle OAuth tokens.

Closes #123
```

### Bug 修复
```
fix(api): handle null response in user endpoint

Fix null pointer exception when user data is not available.
Add null checks and provide default values for user properties.
Update error handling logic to gracefully handle missing data.

Fixes #456
```

### 文档更新
```
docs(readme): update installation guide

Add new installation steps for Windows users.
Update dependency versions in examples.
Add troubleshooting section for common issues.
```

### 重构
```
refactor(utils): extract common validation logic

Extract common validation logic into separate utility functions.
Improve code readability and maintainability.
No functional changes to the public API.
```

### 性能优化
```
perf(database): optimize query performance

Add database indexes for frequently queried fields.
Optimize SQL queries to reduce execution time by 40%.
Improve overall application response time.
```

### 破坏性变更
```
feat(auth): remove deprecated login API

Remove deprecated login API endpoints that were marked for removal.
Update all internal calls to use the new OAuth2 endpoints.

BREAKING CHANGE: The deprecated login API endpoints have been removed.
Migration: Update your client code to use the new OAuth2 endpoints.
See migration guide at https://example.com/migration.
```

## 最佳实践

- 提交信息要清晰明了
- 使用祈使语气（Add, Fix, Update等）
- 标题不超过50字符
- 正文至少20字符（docs 类型除外）
- 必要时提供详细说明和变更动机
- 每个提交只做一件事
- 破坏性变更必须在脚注中声明
- 引用相关的 GitHub issues 和 PR