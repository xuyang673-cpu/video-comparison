# 视频对比工具

一个用于对比两个视频并标记差异的网页工具。

## 功能特性

- 🎬 **双视频同步播放** - 并排显示两个视频，支持同步播放/暂停
- 📝 **自动保存标注** - 选择是否同质化或输入备注时自动保存
- 💾 **本地存储** - 数据自动保存到浏览器本地，下次打开自动加载
- 📊 **Excel导出** - 将标注结果导出为Excel文件
- 📁 **默认数据** - 内置100行视频对比数据，开箱即用

## 使用方法

1. 打开网页后，会自动加载默认数据
2. 使用"上一行"/"下一行"按钮切换视频
3. 点击"同步播放"开始对比视频
4. 选择"是否同质化"（同质化/非同质化/未确定）
5. 填写备注（可选）
6. 标注会自动保存
7. 完成后点击"导出为Excel"保存结果

## 部署说明

本项目使用 GitHub Pages 部署，通过 GitHub Actions 自动部署。

### 部署步骤

1. 将项目推送到 GitHub 仓库
2. 在仓库设置中启用 GitHub Pages：
   - Settings → Pages
   - Source: GitHub Actions
3. 推送到 main 分支后，GitHub Actions 会自动部署

### 访问地址

部署成功后，访问地址为：
```
https://[你的用户名].github.io/[仓库名]/
```

## 技术栈

- HTML5
- CSS3
- JavaScript (原生)
- SheetJS (xlsx.js) - Excel文件处理
- LocalStorage - 本地数据存储

## 文件说明

- `index.html` - 主页面文件
- `default_data.json` - 默认视频数据（100行）
- `.github/workflows/deploy.yml` - GitHub Actions 部署配置
- `.nojekyll` - 禁用 Jekyll 处理

## 注意事项

- 确保 `default_data.json` 文件与 `index.html` 在同一目录
- 视频链接需要支持跨域访问（CORS）
- 浏览器需要支持 LocalStorage
