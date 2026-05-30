# 部署到 GitHub Pages

## 方式一：手动部署

1. **在 GitHub 上新建仓库**
   - 访问 https://github.com/new
   - 输入仓库名，如 `renovation-check`
   - 选择 Public（免费）
   - 创建

2. **推送到 GitHub**
   ```bash
   git init
   git add .
   git commit -m "init: 装修验收记录 PWA"
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git push -u origin main
   ```

3. **启用 GitHub Pages**
   - 进入仓库 Settings → Pages
   - Source 选择 "Deploy from branch"
   - Branch 选择 `main`，目录选 `/ (root)`
   - 点 Save

4. **等待 1-2 分钟**，然后访问：
   `https://<你的用户名>.github.io/<仓库名>/`

## 方式二：使用 gh 命令行

```bash
# 登录 GitHub
gh auth login

# 创建仓库并推送
git init
git add .
git commit -m "init: 装修验收记录 PWA"
gh repo create renovation-check --public --push --source=.

# 启用 Pages
gh api repos/<用户名>/renovation-check/pages -X POST \
  -f source.branch=main -f source.path=/
```

## 手机端使用

- 用手机浏览器（Chrome / Safari）打开 GitHub Pages 地址
- iOS Safari: 点分享按钮 →「添加到主屏幕」
- Android Chrome: 点菜单 →「添加到主屏幕」
- 之后会像一个独立 App 一样使用，支持拍照和离线

## 注意

- 照片全部存在手机浏览器本地，换手机会丢失数据
- 如需要清理数据，在浏览器设置中清除网站数据即可
- 如果更新了代码，重新推送到 GitHub，页面会自动更新（可能需要清除浏览器缓存）
