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

### 4. 团队协作

- **Emoji版本团队**:
  - 统一使用 [`git_emoji.md`](git_emoji.md) 中的表情符号标准
  - 遵循 [`git_commit.md`](git_commit.md) 中的提交规范
  - 使用 [`prompt.md`](prompt.md) 确保AI生成一致的提交信息

- **无Emoji版本团队**:
  - 统一使用 [`git_commit_no_emoji.md`](git_commit_no_emoji.md) 中的类型标识符
  - 遵循 [`git_commit_no_emoji.md`](git_commit_no_emoji.md) 中的提交规范
  - 可以根据需要修改 [`prompt.md`](prompt.md) 以适配无Emoji版本

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