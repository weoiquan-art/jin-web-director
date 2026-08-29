# Performance Checklist

性能优化检查清单，确保网站快速加载和流畅交互。

## ⚡ 快速优化顺序

```
第 1 步: 图片优化 (影响最大, 50% 收益)
  ↓ 压缩 + 格式选择 + 延迟加载
第 2 步: 字体优化 (20% 收益)
  ↓ font-display + 限制字体文件
第 3 步: JS 优化 (15% 收益)
  ↓ 代码分割 + 懒加载
第 4 步: CSS 优化 (10% 收益)
  ↓ 删除未用 + 内联关键样式
第 5 步: 缓存策略 (5% 收益)
  ↓ CDN + 浏览器缓存
```

---

## Lighthouse 目标分数

| 指标 | 目标 | 优先级 |
|------|------|--------|
| Performance | ≥ 90 | ⭐⭐⭐⭐⭐ |
| Accessibility | ≥ 90 | ⭐⭐⭐⭐ |
| Best Practices | ≥ 90 | ⭐⭐⭐ |
| SEO | ≥ 90 | ⭐⭐⭐ |
| PWA | ✓ (可选) | ⭐⭐ |

**检查工具：** Chrome DevTools → Lighthouse

---

## Core Web Vitals (关键指标)

| 指标 | 缩写 | 目标 | 不良 | 修复 |
|------|------|------|------|------|
| 最大内容绘制 | LCP | <2.5s | >4s | 优化服务器, 移除重JS |
| 累积布局偏移 | CLS | <0.1 | >0.25 | 预留空间, 避免浮动 |
| 首次输入延迟 | FID | <100ms | >300ms | 减少 JS, 任务分割 |
| 第一个输入到绘制 | INP | <200ms | >500ms | JS 优化 |

**Lighthouse 会自动检查这些。**

---

## 图片优化 (收益最大)

### 格式选择

| 格式 | 大小 | 质量 | 用在 | 何时用 |
|------|------|------|------|--------|
| WebP | 最小 | ✓✓✓ | 所有摄影图 | 浏览器支持 (99%+) |
| JPG | 中 | ✓✓ | 摄影, 照片 | 低版本浏览器 fallback |
| PNG | 大 | ✓✓✓ | 截图, 无损 | 需要透明度且内容简单 |
| SVG | 最小 | ✓✓✓ | 图标, logo | 矢量图, 可缩放 |
| AVIF | 超小 | ✓✓✓ | 高端设备 | 新浏览器优化 |

**推荐组合：**
```html
<picture>
  <source srcset="img.avif" type="image/avif">
  <source srcset="img.webp" type="image/webp">
  <img src="img.jpg" alt="描述">
</picture>
```

### 图片压缩目标

| 类型 | 宽度 | 文件大小目标 |
|------|------|-----------|
| 英雄图 | 1440px+ | <200KB (WebP) |
| 卡片图 | 400px | <80KB |
| 缩略图 | 200px | <30KB |
| 图标 | <64px | <5KB (SVG) or <10KB |
| 背景图 | full-width | <100KB |

**压缩工具：**
- TinyPNG / TinyJPG (Web UI)
- ImageOptim (Mac)
- Squoosh (Google, Web)
- cwebp (CLI WebP)

### 延迟加载 (Lazy Loading)

```html
<!-- 原生延迟加载 (所有现代浏览器) -->
<img src="..." loading="lazy" alt="描述">

<!-- 关键图片不延迟 -->
<img src="hero.jpg" alt="Hero" loading="eager">

<!-- Intersection Observer (高级控制) -->
<img data-src="..." class="lazy-load" alt="描述">
<script>
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.src = e.target.dataset.src;
        observer.unobserve(e.target);
      }
    });
  });
  document.querySelectorAll('.lazy-load').forEach(img => observer.observe(img));
</script>
```

---

## 字体优化 (20% 收益)

### Font-Display 策略

| 策略 | 行为 | 用在 | 优先级 |
|------|------|------|--------|
| `swap` | 立即显示系统字体, 替换 | 正文, 优先 | ⭐⭐⭐⭐⭐ |
| `fallback` | 短超时后用系统字体 | 标题 | ⭐⭐⭐ |
| `optional` | 后台加载, 可能不用 | 装饰性 | ⭐⭐ |
| `auto` | 浏览器默认 (通常延迟) | 不推荐 | ❌ |
| `block` | 隐藏直到字体加载 (最慢) | 不推荐 | ❌ |

**推荐用法：**
```css
@font-face {
  font-family: 'MyFont';
  src: url('font.woff2') format('woff2');
  font-display: swap; /* 立即显示备选字体 */
}
```

### 字体文件优化

| 优化 | 方法 | 收益 |
|------|------|------|
| 格式 | 用 woff2 (最小) 而非 TTF | -60% |
| 子集 | 只加载用到的字符 | -70% |
| 数量 | ≤ 2 字体文件 | 减少网络请求 |
| 变体 | 只加载需要的 (regular, bold) | -50% |

**Google Fonts 示例 (已优化)：**
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
```

---

## JavaScript 优化

### 代码分割 (Code Splitting)

| 策略 | 说明 | 收益 |
|------|------|------|
| 路由分割 | 每个页面/路由单独 bundle | 首屏 -40% |
| 组件分割 | 模态/下拉延迟加载 | 首屏 -20% |
| 依赖分割 | 将大库分离出来 | 缓存命中 +50% |

**动态导入示例 (React)：**
```jsx
const Modal = React.lazy(() => import('./Modal'));

<Suspense fallback={<Loading />}>
  <Modal />
</Suspense>
```

### JS 加载优化

| 属性 | 用法 | 好处 |
|------|------|------|
| `defer` | 异步加载, 页面解析后执行 | 不阻塞渲染 (推荐) |
| `async` | 异步加载, 立即执行 | 最快但可能乱序 |
| `module` | ESM 模块加载 | 现代浏览器最优 |

**推荐：**
```html
<!-- 关键 JS: inline or defer -->
<script defer src="main.js"></script>

<!-- 可选 JS: async -->
<script async src="analytics.js"></script>

<!-- 分析/广告: 最后加载 -->
<script async src="tracking.js"></script>
```

---

## CSS 优化

### 关键 CSS 内联

页面首次加载需要的样式内联在 `<head>`, 其他延迟加载：

```html
<head>
  <!-- 关键 CSS (< 14KB) -->
  <style>
    body { margin: 0; font-family: sans-serif; }
    .hero { background: url(...); }
  </style>

  <!-- 非关键 CSS 异步加载 -->
  <link rel="preload" href="style.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
  <noscript><link rel="stylesheet" href="style.css"></noscript>
</head>
```

### 删除未用 CSS

```bash
# 方案 1: PurgeCSS (自动)
npm install --save-dev purgecss
purgecss --css src/style.css --content src/**/*.html --output dist/

# 方案 2: Tailwind (内置优化)
# 生产构建自动 tree-shake 未用类
```

---

## 缓存策略

### HTTP 缓存头

| 资源 | Cache-Control | 说明 |
|------|----------------|------|
| HTML | max-age=0, must-revalidate | 总是检查更新 |
| CSS/JS | max-age=31536000 | 1 年缓存 (用版本号) |
| 图片 | max-age=31536000 | 1 年缓存 |
| API | max-age=60 | 1 分钟缓存 |

**Nginx 示例：**
```nginx
location ~* \.(js|css|png|jpg|jpeg)$ {
  expires 1y;
  add_header Cache-Control "public, immutable";
}
location / {
  add_header Cache-Control "no-cache, must-revalidate";
}
```

### 版本化资源

```html
<!-- 用哈希版本化 (改内容才改名) -->
<link rel="stylesheet" href="style.abc123.css">
<script src="main.def456.js"></script>

<!-- 或查询参数 -->
<link rel="stylesheet" href="style.css?v=abc123">
```

---

## 性能快速检查清单

在发布前运行：

- [ ] Lighthouse Performance ≥ 90
- [ ] LCP < 2.5s (最大内容绘制)
- [ ] CLS < 0.1 (累积布局偏移)
- [ ] 英雄图 < 200KB (WebP)
- [ ] 总 JS 大小 < 300KB (gzip)
- [ ] 总 CSS 大小 < 100KB (gzip)
- [ ] 字体文件 ≤ 2, 用 woff2
- [ ] font-display: swap 或 fallback
- [ ] 关键图片 loading="eager"
- [ ] 其他图片 loading="lazy"
- [ ] 关键 CSS 内联 < 14KB
- [ ] 无阻塞 JS 在 </body> 之前
- [ ] Core Web Vitals 绿灯 ✓

**运行：** `chrome://inspect → Performance → Record`

---

## 测试工具

| 工具 | 用途 | 访问 |
|------|------|------|
| Lighthouse | 性能综合评分 | Chrome DevTools |
| WebPageTest | 深度诊断 | webpagetest.org |
| Pagespeed Insights | 快速扫描 + 建议 | pagespeed.web.dev |
| GTmetrix | 性能对比 | gtmetrix.com |
| Bundle Analyzer | JS 大小分析 | webpack-bundle-analyzer |

---

## 性能优化优先级

| 优化项 | 时间投入 | 性能收益 | 优先级 |
|--------|---------|---------|--------|
| 图片压缩 + 格式 | 1h | ⭐⭐⭐⭐⭐ 50% | ⭐⭐⭐⭐⭐ |
| 字体优化 | 30min | ⭐⭐⭐⭐ 20% | ⭐⭐⭐⭐ |
| 代码分割 | 2h | ⭐⭐⭐ 15% | ⭐⭐⭐ |
| CSS 内联 | 1h | ⭐⭐⭐ 10% | ⭐⭐⭐ |
| 缓存策略 | 30min | ⭐⭐ 5% | ⭐⭐ |

**建议顺序：** 图片 → 字体 → 代码分割 → CSS → 缓存

---

## 更新历史

| 日期 | 变更 | 说明 |
|------|------|------|
| 2026-08-29 | 初稿 | 创建性能优化检查清单 |
