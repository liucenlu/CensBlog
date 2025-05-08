# 我的博客网站存储库
### 技术选型

本教程选择的技术栈：

- Hexo：博客生成框架，基于Node.js
- GitHub：文件托管平台
- Netlify：站点部署服务（比GitHub Pages在国内访问速度更快）
- Cloudflare：提供CDN加速服务

### 搭建步骤

1. 配置Node.js环境
    - Mac：使用`brew install node`
    - Linux：通过命令行安装
    - Windows：从官网下载安装包（建议在Git Bash中使用）
    - 安装后检查：`node -v`和`npm -v`
    - 可选：将npm源修改为淘宝源加速
2. 安装Hexo框架
    - 全局安装Hexo：`npm install -g hexo-cli`
    - 初始化博客：`hexo init 博客路径`
    - 安装依赖：`cd 博客路径` 然后 `npm install`
    - 修改package.json，添加Netlify构建命令
3. 推送到GitHub
    - 创建GitHub仓库
    - 将本地博客目录推送到GitHub
4. Netlify建站
    - 注册登录Netlify（需科学上网）
    - 连接GitHub仓库
    - 构建命令设置为`npm run netlify`
    - 获取netlify.app域名
5. 配置自定义域名
    - 在域名服务商处配置CNAME解析
    - 在Netlify配置个人域名
    - 开启Netlify的CDN服务
6. Cloudflare加速配置
    - 注册登录Cloudflare
    - 添加自己的域名
    - 修改DNS服务器为Cloudflare提供的服务器
    - 在Netlify配置HTTPS访问
