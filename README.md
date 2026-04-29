# 个人主页 + 博客

基于 Astro 构建的现代化个人主页和博客系统。

## 特性

- 🚀 **高性能** - 零 JavaScript 运行时，极速加载
- 🎨 **响应式设计** - 完美适配移动端和桌面端
- 🌓 **深色模式** - 支持自动和手动主题切换
- 📝 **博客系统** - 完整的 Markdown 博客支持
- 🔍 **SEO 优化** - 内置 SEO 元标签和站点地图
- ♿ **无障碍** - 遵循 WCAG 标准
- 📦 **TypeScript** - 完整的类型支持

## 项目结构

```
personalPage/
├── src/
│   ├── pages/              # 页面文件
│   │   ├── index.astro     # 个人主页
│   │   ├── about.astro     # 关于页面
│   │   ├── projects.astro  # 项目作品页面
│   │   └── blog/
│   │       ├── index.astro     # 博客列表
│   │       └── [slug].astro    # 博客详情
│   ├── components/         # 可复用组件
│   │   ├── Header.astro    # 头部导航
│   │   ├── Footer.astro    # 页脚
│   │   ├── ThemeToggle.astro # 主题切换
│   │   ├── BlogPostCard.astro # 博客卡片
│   │   ├── ProjectCard.astro  # 项目卡片
│   │   └── SkillBar.astro     # 技能条
│   ├── layouts/
│   │   └── BaseLayout.astro   # 基础布局
│   ├── content/
│   │   └── blog/              # 博客文章
│   ├── styles/
│   │   └── global.css         # 全局样式
│   └── config.ts              # 站点配置
├── public/                    # 静态资源
├── astro.config.mjs          # Astro 配置
├── tailwind.config.mjs       # Tailwind CSS 配置
└── tsconfig.json             # TypeScript 配置
```

## 快速开始

### 安装依赖

```bash
npm install
```

### 开发模式

```bash
npm run dev
```

访问 http://localhost:4321/

### 构建生产版本

```bash
npm run build
```

### 预览生产构建

```bash
npm run preview
```

## 配置

编辑 `src/config.ts` 文件来定制你的个人信息：

```typescript
export const SITE = {
  title: '我的个人主页',
  author: '你的名字',
  email: 'your.email@example.com',
  bio: '你的简介',
  avatar: '/avatar.jpg',
  social: {
    github: 'https://github.com/yourusername',
    twitter: 'https://twitter.com/yourusername',
    // ...
  },
};
```

## 创建博客文章

在 `src/content/blog/` 目录下创建 `.md` 文件：

```markdown
---
title: '文章标题'
description: '文章描述'
pubDate: 2024-01-15
heroImage: '/blog/cover.jpg'
tags: ['标签 1', '标签 2']
categories: ['分类']
draft: false
readingTime: 8
---

文章内容...
```

## 自定义样式

项目使用 Tailwind CSS，可以通过以下方式自定义：

1. 编辑 `tailwind.config.mjs` 修改主题
2. 编辑 `src/styles/global.css` 添加自定义样式
3. 使用 CSS 变量实现深色模式支持

## 部署

### Netlify

1. 连接 GitHub 仓库
2. 构建设置：
   - Build command: `npm run build`
   - Publish directory: `dist`

### Vercel

1. 导入项目
2. 自动检测 Astro 配置
3. 一键部署

### 其他平台

```bash
npm run build
# 上传 dist 目录到任何静态托管服务
```

## 技术栈

- [Astro](https://astro.build/) - 静态站点生成器
- [Tailwind CSS](https://tailwindcss.com/) - CSS 框架
- [TypeScript](https://www.typescriptlang.org/) - 类型系统
- [Shiki](https://github.com/shikijs/shiki) - 代码高亮

## 许可证

MIT
