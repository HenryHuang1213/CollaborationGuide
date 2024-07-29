# CollaborationGuide ｜GitHub 项目协作指南

## 1. 创建新的 GitHub 仓库

1. 登录到 GitHub 账户。
2. 点击右上角的 "+" 图标，选择 "New repository"。
3. 填写仓库名称、描述，选择是否公开。
4. 选择 "Initialize this repository with a README"。
5. 点击 "Create repository"。

## 2. 克隆仓库到本地

```bash
git clone https://github.com/你的用户名/仓库名.git
cd 仓库名
```

## 3. 创建并切换到 dev 分支

```bash
git checkout -b dev
git push -u origin dev
```

## 4. 工作流程

### 4.1 开始新的功能开发

1. 从 dev 分支创建新的功能分支：
   ```bash
   git checkout dev
   git pull
   git checkout -b feature/新功能名
   ```

2. 在新分支上进行开发。

### 4.2 提交变更

1. 查看修改：
   ```bash
   git status
   git diff
   ```

2. 暂存修改：
   ```bash
   git add .
   ```

3. 提交修改：
   ```bash
   git commit -m "描述性的提交信息"
   ```

4. 推送到远程仓库：
   ```bash
   git push origin feature/新功能名
   ```

### 4.3 创建合并请求（MR）

1. 在 GitHub 上，切换到你的功能分支。
2. 点击 "Compare & pull request"。
3. 选择目标分支为 dev。
4. 填写 MR 描述，详细说明你的修改。
5. 点击 "Create pull request"。

### 4.4 代码审查

1. 团队成员审查代码，提供反馈。
2. 根据反馈进行必要的修改。
3. 推送新的修改到同一分支。

### 4.5 合并到 dev 分支

1. 在所有审查者批准后，合并 MR 到 dev 分支。
2. 删除功能分支（可选）。

## 5. 最佳实践

### 5.1 提交规范

- 每次提交应该专注于一个特定的改动。
- 提交信息应该清晰、简洁地描述改动内容。
- 避免在一次提交中包含无关的改动（如删除多余空行）。

### 5.2 代码审查注意事项

- 仔细检查每个文件的变更。
- 确保所有改动都是必要的，且与当前任务相关。
- 提供建设性的反馈，包括代码质量、性能和可读性方面的建议。

### 5.3 分支管理

- 主分支（main）：仅用于稳定、可发布的代码。
- 开发分支（dev）：日常开发的主要分支。
- 功能分支：从 dev 分支创建，用于开发新功能。

## 6. 常见问题解决

### 6.1 处理合并冲突

1. 拉取最新的 dev 分支：
   ```bash
   git checkout dev
   git pull
   ```

2. 切换回你的功能分支并合并 dev：
   ```bash
   git checkout feature/your-feature
   git merge dev
   ```

3. 解决冲突，然后提交解决后的文件：
   ```bash
   git add .
   git commit -m "解决与 dev 分支的合并冲突"
   ```

4. 推送更新后的分支：
   ```bash
   git push origin feature/your-feature
   ```

### 6.2 撤销最后一次提交

如果你的最后一次提交包含了不必要的改动：

```bash
git reset HEAD~1
```

这将撤销最后一次提交，但保留更改。然后你可以重新暂存和提交正确的更改。

## 7. 结语

遵循这个工作流程将帮助团队更有效地协作，保持代码库的整洁和可维护性。记住，良好的沟通和频繁的小型提交是成功协作的关键。
