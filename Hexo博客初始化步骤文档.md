# Hexo博客初始化完整步骤文档

## 📋 项目概述

本文档详细记录了在 `central-expansion` 目录下创建和配置Hexo博客的完整过程，包括环境准备、项目初始化、配置和本地运行等步骤。

## 🛠️ 环境准备

### 1. 系统要求
- **操作系统**: Windows 10/11
- **Node.js**: v20.18.0 或更高版本
- **npm**: 11.3.0 或更高版本
- **Git**: 2.47.0 或更高版本

### 2. 环境检查命令
```bash
# 检查Node.js版本
node --version

# 检查npm版本
npm --version

# 检查Git版本
git --version
```

**预期输出**:
```
v20.18.0
11.3.0
git version 2.47.0.windows.1
```

## 🚀 项目初始化步骤

### 步骤1: 全局安装Hexo CLI

```bash
# 全局安装Hexo命令行工具
npm install -g hexo-cli

# 验证安装
hexo --version
```

**预期输出**:
```
hexo-cli: 4.3.2
os: win32 10.0.26100 undefined
node: 20.18.0
...
```

### 步骤2: 创建Hexo项目

```bash
# 进入目标目录
cd D:\yamibuy\central-expansion

# 创建新的Hexo项目
hexo init hexo-blog-new

# 进入项目目录
cd hexo-blog-new
```

**项目结构**:
```
hexo-blog-new/
├── _config.yml          # 主配置文件
├── _config.landscape.yml # 主题配置文件
├── package.json         # 项目依赖
├── scaffolds/           # 模板文件夹
│   ├── draft.md
│   ├── page.md
│   └── post.md
├── source/              # 源文件目录
│   └── _posts/          # 文章目录
│       └── hello-world.md
├── themes/              # 主题目录
└── node_modules/        # 依赖包目录
```

### 步骤3: 安装项目依赖

```bash
# 安装项目依赖
npm install

# 如果遇到版本兼容性问题，可以降级到稳定版本
npm uninstall hexo
npm install hexo@7.2.0
```

**注意事项**:
- 如果遇到ES Module兼容性问题，建议使用Hexo 7.2.0版本
- 确保所有依赖包正确安装

### 步骤4: 配置Hexo项目

编辑 `_config.yml` 文件，修改以下配置：

```yaml
# Site
title: 我的新博客
subtitle: '分享技术与生活'
description: '一个全新的技术博客，记录学习与成长'
keywords: '博客,技术,学习,Hexo'
author: 你的名字
language: zh-CN
timezone: 'Asia/Shanghai'

# URL (本地开发)
url: http://localhost:4000
```

**配置说明**:
- `title`: 网站标题
- `subtitle`: 网站副标题
- `description`: 网站描述
- `keywords`: 网站关键词
- `author`: 作者名称
- `language`: 网站语言（zh-CN为中文）
- `timezone`: 时区设置
- `url`: 网站URL（本地开发使用localhost:4000）

### 步骤5: 生成静态文件

```bash
# 生成静态文件
npx hexo generate
```

**预期输出**:
```
INFO  Validating config
INFO  Start processing
INFO  Files loaded in 183 ms
INFO  Generated: archives/index.html
INFO  Generated: index.html
INFO  Generated: archives/2025/10/index.html
INFO  Generated: css/style.css
INFO  Generated: js/script.js
INFO  Generated: fancybox/jquery.fancybox.min.css
INFO  Generated: archives/2025/index.html
INFO  Generated: fancybox/jquery.fancybox.min.js
INFO  Generated: js/jquery-3.6.4.min.js
INFO  Generated: css/images/banner.jpg
INFO  Generated: 2025/10/02/hello-world/index.html
INFO  11 files generated in 196 ms
```

### 步骤6: 启动本地服务器

```bash
# 启动本地服务器
npx hexo server

# 或者指定端口
npx hexo server --port 4000
```

**预期输出**:
```
INFO  Validating config
INFO  Start processing
INFO  Hexo is running at http://localhost:4000/ . Press Ctrl+C to stop.
INFO  Have a nice day
```

## 🎯 验证成功

### 访问博客
1. 打开浏览器
2. 访问 `http://localhost:4000`
3. 应该能看到Hexo默认的Landscape主题页面
4. 包含一篇示例文章"Hello World"

### 项目文件结构验证
```
hexo-blog-new/
├── _config.yml          ✅ 主配置文件
├── package.json         ✅ 项目依赖配置
├── source/              ✅ 源文件目录
│   └── _posts/          ✅ 文章目录
│       └── hello-world.md ✅ 示例文章
├── themes/              ✅ 主题目录
│   └── landscape/       ✅ 默认主题
├── public/              ✅ 生成的静态文件
└── node_modules/        ✅ 依赖包
```

## 📝 常用命令

### 开发命令
```bash
# 创建新文章
npx hexo new "文章标题"

# 创建新页面
npx hexo new page "页面名称"

# 清理缓存
npx hexo clean

# 生成静态文件
npx hexo generate

# 启动本地服务器
npx hexo server

# 组合命令（清理+生成+启动）
npx hexo clean && npx hexo generate && npx hexo server
```

### 部署命令
```bash
# 部署到GitHub Pages（需要先配置）
npx hexo deploy

# 组合命令（清理+生成+部署）
npx hexo clean && npx hexo generate && npx hexo deploy
```

## 🔧 常见问题解决

### 问题1: 版本兼容性错误
**错误信息**: `Error [ERR_REQUIRE_ESM]: require() of ES Module`

**解决方案**:
```bash
npm uninstall hexo
npm install hexo@7.2.0
```

### 问题2: 依赖安装失败
**解决方案**:
```bash
# 清理缓存
npm cache clean --force

# 重新安装
npm install
```

### 问题3: 服务器启动失败
**解决方案**:
```bash
# 检查端口是否被占用
netstat -an | findstr :4000

# 使用其他端口
npx hexo server --port 4001
```

### 问题4: 静态文件生成失败
**解决方案**:
```bash
# 清理缓存后重新生成
npx hexo clean
npx hexo generate
```

## 🎨 主题配置

### 默认主题: Landscape
- 简洁的响应式设计
- 支持文章分类和标签
- 内置搜索功能
- 支持代码高亮

### 更换主题
1. 下载主题到 `themes/` 目录
2. 修改 `_config.yml` 中的 `theme` 配置
3. 重新生成和启动

```yaml
# 在 _config.yml 中修改
theme: 主题名称
```

## 📚 下一步操作

### 1. 创建第一篇文章
```bash
npx hexo new "我的第一篇文章"
```

### 2. 编辑文章内容
编辑 `source/_posts/我的第一篇文章.md` 文件

### 3. 自定义配置
- 修改 `_config.yml` 中的网站信息
- 配置主题设置
- 添加插件和功能

### 4. 部署到线上
- 配置GitHub Pages
- 设置自动部署
- 绑定自定义域名

## 🎉 总结

通过以上步骤，我们成功创建了一个完整的Hexo博客项目，包括：

✅ **环境准备**: Node.js, npm, Git, Hexo CLI  
✅ **项目初始化**: 创建项目结构和安装依赖  
✅ **配置优化**: 中文化配置和本地开发设置  
✅ **本地运行**: 成功启动本地服务器  
✅ **功能验证**: 确认博客可以正常访问  

**项目位置**: `D:\yamibuy\central-expansion\hexo-blog-new`  
**访问地址**: `http://localhost:4000`  
**状态**: ✅ 运行正常

现在你可以开始编写博客文章，享受Hexo带来的便捷博客体验！

---

*文档生成时间: 2025年1月2日*  
*Hexo版本: 7.2.0*  
*Node.js版本: 20.18.0*
