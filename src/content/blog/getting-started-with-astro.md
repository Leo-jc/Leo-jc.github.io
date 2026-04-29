---
title: '使用 Astro 构建个人博客'
description: '学习如何使用 Astro 框架快速搭建高性能的个人博客网站'
pubDate: 2024-01-15
heroImage: 'https://picsum.photos/seed/astro/800/600'
tags: ['Astro', '博客', '前端']
categories: ['技术教程']
draft: false
readingTime: 8
---

## 为什么选择 Astro？

Astro 是一个现代化的静态站点生成器，它具有以下优势：

### 1. 零 JavaScript 运行时

Astro 默认不发送任何 JavaScript 到客户端，这意味着你的网站加载速度非常快。

### 2. 组件 Islands 架构

你可以按需加载交互式的组件，只在需要的地方使用 JavaScript。

### 3. 支持多种框架

Astro 支持 React、Vue、Svelte 等多种前端框架，你可以在同一个项目中使用它们。

## 快速开始

### 安装 Astro

```bash
npm create astro@latest
```

### 项目结构

```
src/
├── pages/        # 页面文件
├── components/   # 可复用组件
├── layouts/      # 布局模板
└── content/      # Markdown 内容
```

## 创建博客页面

Astro 支持使用 Markdown 和 MDX 来编写博客文章。你只需要在 `src/content/blog` 目录下创建 `.md` 文件即可。

### 文章 Frontmatter

```yaml
---
title: '文章标题'
description: '文章描述'
pubDate: 2024-01-15
tags: ['标签 1', '标签 2']
---
```

## 总结

Astro 是一个非常适合构建内容驱动网站的工具，特别是博客、文档站点等。它的性能优势和开发体验都非常出色。
