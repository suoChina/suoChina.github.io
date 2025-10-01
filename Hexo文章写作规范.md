# Hexo文章写作规范与指南

## 📝 创建新文章

### 1. 基本命令
```bash
# 创建新文章
npx hexo new "文章标题"

# 创建草稿（不会发布）
npx hexo new draft "草稿标题"

# 创建页面
npx hexo new page "页面名称"
```

### 2. 文章文件位置
- **已发布文章**: `source/_posts/文章标题.md`
- **草稿文章**: `source/_drafts/草稿标题.md`
- **页面文件**: `source/页面名称/index.md`

## 📋 文章Front-matter规范

### 基本格式
```yaml
---
title: 文章标题
date: 2025-10-02 01:04:46
updated: 2025-10-02 01:04:46
tags: [标签1, 标签2, 标签3]
categories: [分类1, 分类2]
description: 文章描述
keywords: 关键词1, 关键词2
author: 作者名称
permalink: 自定义链接
comments: true
toc: true
mathjax: true
---
```

### 字段说明

| 字段 | 必填 | 说明 | 示例 |
|------|------|------|------|
| `title` | ✅ | 文章标题 | `"我的第一篇技术文章"` |
| `date` | ✅ | 发布日期 | `2025-10-02 01:04:46` |
| `updated` | ❌ | 更新日期 | `2025-10-02 15:30:00` |
| `tags` | ❌ | 标签（数组） | `[JavaScript, 前端, 教程]` |
| `categories` | ❌ | 分类（数组） | `[技术, 前端开发]` |
| `description` | ❌ | 文章描述 | `"详细介绍JavaScript基础语法"` |
| `keywords` | ❌ | 关键词 | `"JavaScript, 语法, 基础"` |
| `author` | ❌ | 作者 | `"你的名字"` |
| `permalink` | ❌ | 自定义链接 | `"my-first-tech-article"` |
| `comments` | ❌ | 是否开启评论 | `true/false` |
| `toc` | ❌ | 是否显示目录 | `true/false` |
| `mathjax` | ❌ | 是否支持数学公式 | `true/false` |

## 📖 文章内容规范

### 1. Markdown语法规范

#### 标题层级
```markdown
# 一级标题（文章标题，通常不用）
## 二级标题（主要章节）
### 三级标题（子章节）
#### 四级标题（详细内容）
```

#### 代码块
```markdown
# 行内代码
`console.log('Hello World')`

# 代码块
```javascript
function hello() {
    console.log('Hello World');
}
```

# 带行号的代码块
```javascript
function hello() {
    console.log('Hello World');
}
```
```

#### 列表
```markdown
# 无序列表
- 项目1
- 项目2
  - 子项目2.1
  - 子项目2.2

# 有序列表
1. 第一步
2. 第二步
3. 第三步
```

#### 链接和图片
```markdown
# 链接
[链接文本](https://example.com)
[内部链接](/path/to/page)

# 图片
![图片描述](图片URL)
![图片描述](/path/to/image.jpg)

# 带链接的图片
[![图片描述](图片URL)](链接URL)
```

### 2. 文章结构规范

#### 标准文章结构
```markdown
---
title: 文章标题
date: 2025-10-02 01:04:46
tags: [标签1, 标签2]
categories: [分类]
description: 文章描述
---

# 文章标题

## 引言
简要介绍文章内容和背景...

## 主要内容

### 章节1
详细内容...

### 章节2
详细内容...

## 总结
总结文章要点...

## 参考资料
- [链接1](URL1)
- [链接2](URL2)
```

## 🎨 文章示例

### 完整文章示例
我已经为你创建了一篇完整的示例文章：`我的第一篇技术文章.md`，展示了：

- ✅ 完整的Front-matter配置
- ✅ 标准的文章结构
- ✅ Markdown语法使用
- ✅ 代码块和语法高亮
- ✅ 链接和列表格式

## 📝 写作流程

### 1. 创建文章
```bash
npx hexo new "文章标题"
```

### 2. 编辑文章
编辑 `source/_posts/文章标题.md` 文件

### 3. 本地预览
```bash
# 启动本地服务器
npx hexo server

# 访问 http://localhost:4000 查看效果
```

### 4. 发布文章
```bash
# 生成静态文件
npx hexo generate

# 部署到线上（如果配置了部署）
npx hexo deploy
```

## 🎯 最佳实践

### 1. 文章命名规范
- 使用有意义的标题
- 避免特殊字符
- 建议使用中文或英文，避免混合

### 2. 标签和分类
- **标签**: 3-5个，描述文章内容关键词
- **分类**: 1-3个，按主题分类
- 保持一致性，建立标签体系

### 3. 文章结构
- 引言：介绍文章背景和目的
- 主体：详细内容，使用清晰的标题层级
- 总结：回顾要点和收获
- 参考资料：相关链接和资源

### 4. 内容质量
- 内容要有价值，解决实际问题
- 使用清晰的逻辑结构
- 适当使用代码示例和图表
- 保持文章的可读性

## 🔧 高级功能

### 1. 数学公式
```yaml
# 在Front-matter中启用
mathjax: true
```

```markdown
# 行内公式
$E = mc^2$

# 块级公式
$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$
```

### 2. 目录生成
```yaml
# 在Front-matter中启用
toc: true
```

### 3. 草稿功能
```bash
# 创建草稿
npx hexo new draft "草稿标题"

# 发布草稿
npx hexo publish "草稿标题"
```

### 4. 文章摘要
```markdown
<!-- more -->
```
在需要截断的地方添加此标签，用于首页显示摘要。

## 📊 文章管理

### 常用命令
```bash
# 列出所有文章
npx hexo list post

# 列出所有页面
npx hexo list page

# 列出所有草稿
npx hexo list draft

# 删除文章
npx hexo delete "文章标题"
```

### 文章统计
- 文章数量：`source/_posts/` 目录下的文件数
- 分类数量：`source/categories/` 目录
- 标签数量：`source/tags/` 目录

## 🎉 总结

通过以上规范，你可以：

1. ✅ 创建结构化的文章
2. ✅ 使用标准的Markdown语法
3. ✅ 配置完整的Front-matter
4. ✅ 遵循最佳实践
5. ✅ 利用高级功能

**现在你可以开始写作了！** 🚀

---

*文档更新时间: 2025年10月2日*
