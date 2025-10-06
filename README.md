<div align="center">
  <picture>
    <img src="./assets/logo.jpg" width="100%">
  </picture>
</div>

<div align="center" style="line-height: 1;">

[![Wechat](https://img.shields.io/badge/Wechat-5EDDD2?style=for-the-badge&logo=wechat&logoColor=7CFC00)](https://github.com/TinkerGeeker/GitEmojiAI/assets/wechat.jpg)
[![GITHUB](https://img.shields.io/badge/Github-24292F?style=for-the-badge&logo=github&logoColor=white)](https://github.com/TinkerGeeker/GitEmojiAI)
[![xiaohongshu](https://img.shields.io/badge/xiaohongshu-FF0000?style=for-the-badge&logo=storybook&logoColor=white)](https://github.com/TinkerGeeker/GitEmojiAI/assets/xiaohongshu.jpg)

</div>

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

### 2. Vibe Coding + 提示词 + 提交规范工作流

#### 核心概念
Vibe Coding + 提示词 + 提交规范是一个完整的 AI 辅助开发工作流，通过环境配置、智能交互和规范化提交，实现高效的 AI 驱动开发。

#### 工作流程三步法

**第一步：选择并配置合适的 Vibe Coding 环境**
- **选择环境**: 根据项目需求选择合适的 AI 编程环境
  - **VS Code + KILO**: 适合需要深度代码交互的项目
  - **Cursor**: 适合需要 AI 原生支持的项目
  - **GitHub Copilot**: 适合需要快速代码补全的项目
- **环境配置**:
  - 安装必要的 AI 插件和工具
  - 配置 API 密钥和访问权限
  - 设置项目特定的提示词模板
- **验证配置**: 确保环境能够正确读取和执行 Git 操作

**第二步：指定仓库 + 提示词**
- **仓库选择**: 确定要操作的 Git 仓库路径
  - 本地仓库路径：`/path/to/your/project`
  - 远程仓库地址：`git@github.com:username/repo.git`
- **提示词配置**: 选择或创建合适的提示词
  - **基础提示词**: 适用于一般开发任务
  - **专业提示词**: 如 GitEmojiAI 中的 [`prompt.md`](projects/GitEmojiAI/prompt.md)
  - **自定义提示词**: 根据项目需求定制
- **参数设置**:
  - 明确任务目标和输出要求
  - 设置约束条件和最佳实践
  - 指定文件路径和操作范围

**第三步：与 Agent 进行交互，完成提交操作**
- **任务输入**: 向 AI Agent 发送具体指令
  - 示例：`请阅读@/projects/GitEmojiAI/prompt.md 对@/projects/GitEmojiAI 进行提交操作`
- **Agent 执行**: AI Agent 按照提示词规范执行操作
  - **文件读取**: 读取相关配置文件和项目文档
  - **状态检查**: 执行 `git status` 和 `git diff` 检查变更
  - **文件操作**: 执行 `git add` 暂存文件
  - **提交生成**: 根据规范生成提交信息
  - **提交执行**: 执行 `git commit` 创建提交
  - **远程推送**: 执行 `git push` 推送到远程仓库
- **结果验证**: 确认操作成功完成
  - 检查提交历史和哈希值
  - 验证远程仓库同步状态

#### 实际应用示例

**场景：初始化 GitEmojiAI 项目**
```
用户输入：请阅读@/projects/GitEmojiAI/prompt.md 对@/projects/GitEmojiAI 进行提交和推送操作

执行过程：
1. KILO 读取 prompt.md → 理解 AI 角色和任务
2. KILO 读取 git_commit.md → 掌握提交规范
3. KILO 读取 git_emoji.md → 了解表情符号选择
4. KILO 执行 git status → 检查仓库状态
5. KILO 执行 git add . → 暂存所有文件
6. KILO 生成提交信息 → :tada: 初始化GitEmojiAI项目
7. KILO 执行 git commit → 创建本地提交
8. KILO 配置远程仓库 → 添加 origin
9. KILO 执行 git push → 推送到远程
```

**场景：日常开发提交**
```
用户输入：请对当前项目进行代码提交，遵循 GitEmojiAI 规范

执行过程：
1. KILO 检查代码变更 → 识别修改的文件
2. KILO 分析变更类型 → 选择合适的表情符号
3. KILO 生成提交信息 → 遵循规范格式
4. KILO 执行提交操作 → 完成版本控制
```

#### 最佳实践
- **环境一致性**: 团队成员使用相同的 Vibe Coding 环境配置
- **提示词标准化**: 建立项目统一的提示词模板
- **提交规范遵守**: 严格按照 Git 提交规范执行
- **版本控制意识**: 定期提交，保持历史记录清晰
- **协作配合**: 确保提交信息清晰明了，便于团队协作

#### 常见问题解决
- **权限问题**: 确保 AI Agent 有足够的 Git 操作权限
- **网络问题**: 检查远程仓库连接和 API 访问
- **规范冲突**: 统一团队提交规范，避免格式不一致
- **环境兼容**: 确保开发环境支持所需的 AI 工具

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