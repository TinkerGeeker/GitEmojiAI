# Git提交规范（无Emoji版本）

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

```
[类型] 简短描述（不超过50字符）

详细说明（可选）
- 变更点1
- 变更点2
- 变更点3
```

### 类型标识符

| 类型 | 标识符 | 说明 |
|------|--------|------|
| 新功能 | `[feat]` | 引入新功能 |
| Bug修复 | `[fix]` | 修复bug |
| 文档更新 | `[docs]` | 添加或更新文档 |
| 代码格式化 | `[style]` | 改进代码格式、不影响功能的变更 |
| 重构 | `[refactor]` | 重构代码，不改变功能 |
| 性能优化 | `[perf]` | 提升性能 |
| 测试相关 | `[test]` | 添加或修改测试代码 |
| 构建工具变动 | `[chore]` | 构建或辅助工具的变动 |
| CI/CD配置 | `[ci]` | CI/CD配置变更 |

### 提交步骤

1. **暂存文件**
    ```bash
    git add .
    # 或者选择特定文件
    git add filename
    ```

2. **提交变更**
    ```bash
    git commit -m "[类型] 提交信息"
    ```

3. **推送远端**
    ```bash
    git push origin main
    # 或者其他分支
    git push origin branch-name
    ```

## 最佳实践

- 提交信息要清晰明了
- 使用祈使语气（Add, Fix, Update等）
- 首字母大写
- 不要超过50字符的标题
- 必要时提供详细说明
- 每个提交只做一件事
- 使用标准的类型标识符

## 示例

```bash
# 新功能提交
git commit -m "[feat] Add user login functionality

- Implement login form
- Add authentication logic
- Update user session handling"

# Bug修复
git commit -m "[fix] Fix null pointer exception in user service"

# 文档更新
git commit -m "[docs] Update API documentation"

# 性能优化
git commit -m "[perf] Optimize database query performance"

# 代码重构
git commit -m "[refactor] Refactor user authentication module"

# 测试相关
git commit -m "[test] Add unit tests for user service"

# 构建工具变动
git commit -m "[chore] Update build dependencies"

# CI/CD配置变更
git commit -m "[ci] Add GitHub Actions workflow for testing"

# 代码格式化
git commit -m "[style] Format code with Prettier"
```

## 与Emoji版本对比

| 特性 | Emoji版本 | 无Emoji版本 |
|------|-----------|------------|
| 格式 | `:emoji: 描述` | `[类型] 描述` |
| 可视化 | 直观，易于识别 | 标准化，易于搜索 |
| 兼容性 | 需要支持emoji的环境 | 所有Git环境都支持 |
| 学习成本 | 需要记忆emoji含义 | 需要记忆类型标识符 |
| 团队协作 | 适合国际化团队 | 适合传统开发团队 |

## 选择建议

- **选择Emoji版本**：如果团队喜欢可视化、直观的提交信息，且工具环境支持emoji
- **选择无Emoji版本**：如果团队偏好标准化、易于搜索的提交信息，或环境不支持emoji
- **混合使用**：可以根据项目或团队的不同需求选择合适的版本