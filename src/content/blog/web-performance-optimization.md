---
title: 'Web 性能优化最佳实践'
description: '全面解析 Web 性能优化的策略和技巧'
pubDate: 2024-03-10
heroImage: 'https://picsum.photos/seed/performance/800/600'
tags: ['性能优化', 'Web', '前端']
categories: ['性能优化']
draft: false
readingTime: 12
---

## 为什么性能很重要？

网站性能直接影响用户体验和业务指标：

- 53% 的移动用户会在页面加载超过 3 秒时离开
- 每增加 100ms 的延迟，亚马逊的销售额就会减少 1%
- Google 将页面速度作为搜索排名的因素

## 核心 Web 指标

### LCP (Largest Contentful Paint)

最大内容绘制，应该在 2.5 秒内完成。

**优化策略：**
- 优化服务器响应时间
- 预加载关键资源
- 优化图片加载

### FID (First Input Delay)

首次输入延迟，应该小于 100 毫秒。

**优化策略：**
- 减少 JavaScript 执行时间
- 使用 Web Workers
- 代码分割

### CLS (Cumulative Layout Shift)

累积布局偏移，应该小于 0.1。

**优化策略：**
- 为图片和视频设置尺寸
- 避免动态插入内容
- 使用字体加载策略

## 实用优化技巧

### 1. 图片优化

```html
<!-- 使用现代图片格式 -->
<picture>
  <source srcset="image.webp" type="image/webp">
  <img src="image.jpg" alt="description">
</picture>

<!-- 懒加载 -->
<img src="image.jpg" loading="lazy" alt="description">
```

### 2. 代码分割

使用动态导入实现代码分割：

```javascript
const module = await import('./heavy-module.js');
```

### 3. 缓存策略

```javascript
// Service Worker 缓存
self.addEventListener('fetch', (event) => {
  event.respondWith(
    caches.match(event.request).then((response) => {
      return response || fetch(event.request);
    })
  );
});
```

### 4. 资源预加载

```html
<!-- 预加载关键资源 -->
<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>
<link rel="prefetch" href="next-page.js" as="script">
```

## 性能监控工具

- **Lighthouse** - Google 的自动化审计工具
- **WebPageTest** - 详细的性能分析
- **Chrome DevTools** - 实时性能分析
- **Core Web Vitals** - Google Search Console

## 总结

性能优化是一个持续的过程，需要不断测量、分析和改进。
