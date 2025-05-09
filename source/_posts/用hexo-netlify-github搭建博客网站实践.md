---
title: 用hexo+netlify+github搭建博客网站实践
date: 2025-05-09 16:54:32
tags:
---

### 博客系统组成

个人博客由四个核心部分组成：

1. 博客生成框架：将用户简单输入转化为完整网站（HTML、CSS、JS）
2. 文件托管平台：将文件存储在云端并提供访问修改接口
3. 站点部署服务：将网站部署到互联网供他人访问
4. 访问加速服务：通过CDN提高网站访问速度

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

### 下一步建议

完成基础搭建后，可以:

- [ ]  进一步美化和装饰个人博客
- [ ]  开始撰写高质量内容
- [ ]  将博客地址分享到评论区与他人交流

		

## hexo

### 常用命令

1. 创建post
    
    ```bash
    hexo new "My New Post"
    ```
    
2. 启动服务
    
    ```bash
    hexo serve
    hexo s  # 简写
    hexo s -w  # 监听源文件的变化 
    ```
    
3. 生成静态文件
    
    ```bash
    hexo generate
    ```
    
4. 部署远程网站
    
    ```bash
    hexo deploy
    ```
    

## 更换主题

在官网[Themes | Hexo](https://hexo.io/themes/)找到喜欢的主题

![image.png](attachment:6fdafaf4-83e0-4460-bd6d-f05efd49e635:image.png)

主题文档会提供下载方式，推荐使用npm下载，复制命令到博客文件夹根目录执行即可。

然后在总配置文件中找到`theme`配置项，修改为新配置的主题名，最后新建一个主题配置文件，填入主题文档中提供的配置内容即可。

![image.png](attachment:c8a5e3a4-5772-44fa-a164-3413f0ec45df:image.png)