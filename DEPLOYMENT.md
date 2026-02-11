# GitHub Pages 部署指南

## 前置准备

1. 确保你有一个 GitHub 账号
2. 确保项目已经初始化 Git 仓库

## 部署步骤

### 1. 创建 GitHub 仓库

1. 登录 GitHub
2. 点击右上角的 "+" → "New repository"
3. 填写仓库名称（例如：`video-comparison`）
4. 选择 Public（GitHub Pages 免费版需要公开仓库）
5. **不要**勾选 "Initialize this repository with a README"
6. 点击 "Create repository"

### 2. 初始化并推送代码

在项目目录下执行以下命令：

```bash
# 初始化 Git（如果还没有）
git init

# 添加所有文件
git add .

# 提交代码
git commit -m "Initial commit: 视频对比工具"

# 添加远程仓库（替换 YOUR_USERNAME 和 REPO_NAME）
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git

# 推送到 main 分支
git branch -M main
git push -u origin main
```

### 3. 启用 GitHub Pages

1. 进入仓库页面
2. 点击 "Settings"（设置）
3. 在左侧菜单中找到 "Pages"
4. 在 "Source" 部分：
   - 选择 "GitHub Actions"
5. 保存设置

### 4. 验证部署

1. 推送代码后，GitHub Actions 会自动开始部署
2. 在仓库页面点击 "Actions" 标签页查看部署状态
3. 部署成功后，访问地址为：
   ```
   https://YOUR_USERNAME.github.io/REPO_NAME/
   ```

## 更新部署

每次推送到 `main` 分支时，GitHub Actions 会自动重新部署：

```bash
git add .
git commit -m "更新说明"
git push origin main
```

## 常见问题

### 1. 404 错误

- 确保仓库是 Public（公开）
- 等待几分钟让 GitHub Pages 生效
- 检查 GitHub Actions 是否部署成功

### 2. 文件找不到

- 确保 `default_data.json` 文件在根目录
- 检查文件路径是否正确

### 3. 部署失败

- 检查 `.github/workflows/deploy.yml` 文件是否存在
- 查看 GitHub Actions 的日志信息
- 确保有正确的权限设置

## 参考项目

本项目参考了以下项目的部署方式：
- `实拍视频审核拉片` - 使用 GitHub Actions 部署
- `videotool` - 使用 GitHub Actions 部署
- `jarvis-admin-master` - 使用 GitHub Actions 部署

## 注意事项

- GitHub Pages 免费版只支持公开仓库
- 部署可能需要几分钟时间
- 确保所有必要的文件都已提交到仓库
