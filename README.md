# GitEmojiAI

通过Vibe Coding+提示词+Git提交规范完成Git自动化

## 项目描述

GitEmojiAI 是一个专为AI设计的工具包，帮助AI通过规范化的Git提交表情符号和提交格式，实现自动化的Git版本控制操作。该项目结合了Gitmoji标准和自定义提交规范，使AI能够生成符合团队标准的提交信息。

## 文件结构与依赖关系

```
prompt.md (AI提示词)
    ↓ 引用
git_commit.md (Emoji提交规范)
    ↓ 引用
git_emoji.md (表情符号参考)

git_commit_no_emoji.md (无Emoji提交规范)
```

## 文件说明

### [`prompt.md`](prompt.md)
- **作用**: 定义AI助手的角色和任务
- **功能**: 指导AI根据代码变更生成规范化的Git提交信息
- **依赖**: 引用 [`git_commit.md`](git_commit.md) 中的提交规范

### [`git_commit.md`](git_commit.md)
- **作用**: 定义Git提交规范（Emoji版本）和操作流程
- **功能**: 提供基于emoji的提交信息格式、Git操作步骤和最佳实践
- **依赖**: 引用 [`git_emoji.md`](git_emoji.md) 中的表情符号选择指南

### [`git_commit_no_emoji.md`](git_commit_no_emoji.md)
- **作用**: 定义Git提交规范（无Emoji版本）
- **功能**: 提供基于类型标识符的提交信息格式、Git操作步骤和最佳实践
- **依赖**: 独立文件，无外部依赖

### [`git_emoji.md`](git_emoji.md)
- **作用**: 提供表情符号参考和变更类型分类
- **功能**: 为不同类型的提交提供合适的表情符号选择
- **依赖**: 独立资源文件，无外部依赖

### [`README.md`](README.md)
- **作用**: 项目说明文档
- **功能**: 介绍项目结构、使用方法和依赖关系

## 使用方法

### 1. 选择提交规范版本

根据团队需求选择合适的提交规范：

- **Emoji版本**: [`git_commit.md`](git_commit.md) - 适合喜欢可视化、直观提交信息的团队
- **无Emoji版本**: [`git_commit_no_emoji.md`](git_commit_no_emoji.md) - 适合偏好标准化、易于搜索提交信息的团队

### 2. AI工作流集成

将 [`prompt.md`](prompt.md) 集成到您的AI开发环境中，AI将根据代码变更自动生成规范的提交信息。

### 3. 手动使用

#### Emoji版本使用流程：
1. **查看变更**: 使用 `git status` 和 `git diff` 检查变更
2. **选择表情**: 参考 [`git_emoji.md`](git_emoji.md) 选择合适的表情符号
3. **编写提交信息**: 遵循 [`git_commit.md`](git_commit.md) 中的格式规范
4. **执行提交**: 使用 `git commit -m "提交信息"`

#### 无Emoji版本使用流程：
1. **查看变更**: 使用 `git status` 和 `git diff` 检查变更
2. **选择类型**: 参考 [`git_commit_no_emoji.md`](git_commit_no_emoji.md) 选择合适的类型标识符
3. **编写提交信息**: 遵循 [`git_commit_no_emoji.md`](git_commit_no_emoji.md) 中的格式规范
4. **执行提交**: 使用 `git commit -m "提交信息"`

### 4. KILO AI 助手工作流示例

以下是一个完整的示例，展示用户如何通过 GitEmojiAI 项目让 KILO AI 助手完成 Git 提交操作：

#### 用户输入
```
请阅读@/projects/GitEmojiAI/prompt.md 对@/projects/GitEmojiAI 进行提交操作
```

#### KILO 执行步骤

**步骤 1: 阅读提示词文件**
- KILO 读取 [`prompt.md`](prompt.md) 文件
- 理解 AI 助手的角色设定和任务要求
- 获取提交规范和操作指南的引用信息

**步骤 2: 阅读提交规范文件**
- KILO 读取 [`git_commit.md`](git_commit.md) 文件
- 了解 Git 提交规范（Emoji版本）
- 掌握提交信息格式、Git操作步骤和最佳实践
- 获取表情符号选择指南的引用

**步骤 3: 阅读表情符号参考文件**
- KILO 读取 [`git_emoji.md`](git_emoji.md) 文件
- 了解表情符号选择指南和变更类型分类
- 为不同类型的提交提供合适的表情符号选择

**步骤 4: 检查 Git 仓库状态**
- KILO 执行 `git status` 命令
- 查看当前工作目录的变更状态
- 发现5个未跟踪的文件：README.md、git_commit.md、git_commit_no_emoji.md、git_emoji.md、prompt.md

**步骤 5: 分析项目文件**
- KILO 读取所有相关文件内容
- 理解项目结构和文件用途
- 确定这是一个新项目的初始提交

**步骤 6: 暂存文件**
- KILO 执行 `git add .` 命令
- 将所有未跟踪的文件添加到暂存区

**步骤 7: 生成提交信息**
- KILO 根据项目性质选择合适的表情符号 `:tada:`
- 遵循提交规范格式编写提交信息
- 使用祈使语气，首字母大写
- 提交信息不超过50字符
- 提供详细的变更说明

**步骤 8: 执行提交**
- KILO 执行 `git commit -m ":tada: 初始化GitEmojiAI项目..."` 命令
- 完成本地提交操作

**步骤 9: 配置远程仓库**
- KILO 检查远程仓库配置
- 执行 `git remote add origin git@github.com:TinkerGeeker/GitEmojiAI.git` 添加远程仓库

**步骤 10: 推送到远程仓库**
- KILO 执行 `git push origin main` 命令
- 将提交推送到远程仓库

#### 最终结果
- 提交哈希: `e797fd3`
- 提交信息: `:tada: 初始化GitEmojiAI项目`
- 包含5个文件，共479行代码
- 成功推送到远程仓库

## 核心特性

- **模块化设计**: 四个文件职责明确，相互解耦
- **依赖清晰**: 形成单向依赖链，避免循环引用
- **易于维护**: 每个文件可独立更新和扩展
- **AI友好**: 专为AI辅助开发工作流设计

## 最佳实践

1. **保持一致性**: 团队成员统一使用相同的表情符号标准
2. **简洁明了**: 提交信息不超过50字符
3. **使用祈使语气**: 如 "Add", "Fix", "Update" 等
4. **单一职责**: 每个提交只做一件事

## 参考

- [git-commit-emoji-cn](https://github.com/liuchengxu/git-commit-emoji-cn) - Git提交表情符号中文指南
- [gitmoji](https://github.com/carloscuesta/gitmoji) - Gitmoji官方仓库
- [emoji-cheat-sheet](https://github.com/ikatyang/emoji-cheat-sheet) - Emoji速查表

## 贡献

欢迎提交Issue和Pull Request来改进这个项目。

## 许可证

MIT License