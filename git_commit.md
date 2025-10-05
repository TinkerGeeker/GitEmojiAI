# Git提交规范

## 语言配置

- **中文**: 使用中文提交信息和描述

## 提交前准备

1. **查看仓库变动**: 检查当前工作目录的变更状态
    ```bash
    git status
    ```

2. **检查变更内容**: 确认要提交的文件
    ```bash
    git diff
    ```

3. **更新必要文件**: 如有需要，更新README.md或其他文档

## 提交规范

### 提交信息格式

#### Emoji版本

```
:emoji: 简短描述（不超过50字符）

详细说明（可选）
- 变更点1
- 变更点2
- 变更点3
```


### 提交步骤

1. **暂存文件**
    ```bash
    git add .
    # 或者选择特定文件
    git add filename
    ```

2. **提交变更**
    ```bash
    git commit -m ":emoji: 提交信息"
    ```

3. **推送远端**
    ```bash
    git push origin main
    # 或者其他分支
    git push origin branch-name
    ```

## 表情符号选择指南

请参考 [`git_emoji.md`](git_emoji.md) 文件，根据不同的变更类型选择合适的表情符号。该文件提供了完整的表情符号列表及其对应的变更类型说明。

## 最佳实践

- 提交信息要清晰明了
- 使用祈使语气（Add, Fix, Update等）
- 首字母大写
- 不要超过50字符的标题
- 必要时提供详细说明
- 每个提交只做一件事

## 示例

```bash
# 新功能提交
git commit -m ":sparkles: Add user login functionality

- Implement login form
- Add authentication logic
- Update user session handling"

# Bug修复
git commit -m ":bug: Fix null pointer exception in user service"

# 文档更新
git commit -m ":memo: Update API documentation"

# 性能优化
git commit -m ":zap: Optimize database query performance"

# 代码重构
git commit -m ":recycle: Refactor user authentication module"
