# Responsive Decision Matrix

响应式设计决策矩阵，快速确定各断点的布局策略。省 token 版本。

## 响应式设计决策流程

```
内容类型是什么?
├─ 导航 (nav)
│   ├─ 375px:  汉堡菜单 (3 线条)
│   ├─ 768px:  汉堡或水平栏
│   └─ 1440px: 水平导航 + 辅助菜单
│
├─ 英雄区 (hero)
│   ├─ 375px:  单栏 (图片/文字上下)
│   ├─ 768px:  2 栏 (50/50 or 40/60)
│   └─ 1440px: 2-3 栏或全宽
│
├─ 卡片列表 (card grid)
│   ├─ 375px:  1 列, 8px 边距
│   ├─ 768px:  2 列, 12px 沟槽
│   └─ 1440px: 3-4 列, 16px 沟槽
│
├─ 表格 (table)
│   ├─ 375px:  卡片格式 (垂直堆栈)
│   ├─ 768px:  可横向滚动 or 删除非关键列
│   └─ 1440px: 原生表格布局
│
├─ 表单 (form)
│   ├─ 375px:  单列, 100% 宽输入框
│   ├─ 768px:  2 列, 必要时堆栈
│   └─ 1440px: 2-3 列或 1 列中心布局
│
└─ 页脚 (footer)
    ├─ 375px:  垂直堆栈, 单列链接
    ├─ 768px:  2-3 列
    └─ 1440px: 多列网格
```

---

## 断点速查表

| 设备 | 断点名 | 宽度 | 栅格列 | 典型使用 |
|------|--------|------|--------|---------|
| 手机 | xs | 375px | 1-2 | iPhoneSE, 小屏 |
| 大手机 | sm | 600px | 2 | iPhone 13+ |
| 平板竖 | md | 768px | 3-4 | iPad Air 竖向 |
| 平板横 | lg | 1024px | 4-6 | iPad 横向, 小笔记本 |
| 笔记本 | xl | 1440px | 6-12 | 普通笔记本 |
| 大屏 | 2xl | 1920px+ | 12+ | 桌面, 外接显示器 |

---

## 内容类型布局矩阵

### Navigation (导航)

| 元素 | 375px | 768px | 1440px |
|------|-------|-------|--------|
| 菜单 | 汉堡 (✓) | 汉堡/水平选项 | 水平导航 (完整) |
| Logo | 左对齐, 24px | 左对齐, 28px | 左对齐, 32px |
| 用户菜单 | 右汉堡内 | 右侧/汉堡 | 右上角 |
| 搜索 | 只有 icon | icon/展开 | 完整输入框 |

**代码示例：**
```html
<!-- 导航容器宽度 -->
<nav class="navbar">
  <!-- xs: 100vw, sm+: max-width 1440px -->
</nav>
```

---

### Hero Section (英雄区)

| 属性 | 375px | 768px | 1440px |
|------|-------|-------|--------|
| 布局 | 单栏 (图上/下) | 2 栏 (50/50) | 2-3 栏 (40/60) |
| 图片宽度 | 100% | 50% | 60% |
| 内容宽度 | 100% | 50% | 40% |
| 高度 | 60vh | 50vh | 70vh |
| 文字大小 | H2 (2.4rem) | H1 (3.2rem) | H1 (4rem) |
| 边距 | 16px | 24px | 32px |

---

### Card Grid (卡片列表)

| 指标 | 375px | 768px | 1440px |
|------|-------|-------|--------|
| 列数 | 1 | 2 | 3-4 |
| 沟槽 | 8px | 12px | 16px |
| 卡片边距 | 8px (外) | 12px | 16px |
| 每卡高度 | auto | auto | 固定 or auto |
| 边框半径 | 4px | 8px | 8px |

**Flexbox 方式：**
```css
.card-grid {
  display: grid;
  gap: 16px;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

/* 或按断点 */
@media (max-width: 768px) {
  .card-grid { grid-template-columns: 1fr; }
}
```

---

### Table (表格)

| 处理方式 | 375px | 768px | 1440px |
|---------|-------|-------|--------|
| 布局 | 卡片 (vertical) | 可滚动 or 卡片 | 原生表格 |
| 列数显示 | 1-2 关键列 | 3-4 列 | 全部列 |
| 操作 (删除/编辑) | 下拉菜单 | 按钮/下拉 | 行内按钮 |

**卡片模式 (375px)：**
```html
<div class="table-card">
  <div class="row"> <span class="label">Name</span> <span>John</span> </div>
  <div class="row"> <span class="label">Email</span> <span>john@ex.com</span> </div>
</div>
```

---

### Form (表单)

| 属性 | 375px | 768px | 1440px |
|------|-------|-------|--------|
| 列数 | 1 | 1-2 | 2-3 |
| 输入宽度 | 100% | 100% or 48% | 32% or 100% 组合 |
| 标签位置 | 上方 | 上方 or 左侧 | 左侧或上方 |
| 按钮宽度 | 100% | 50%-100% | auto or 200px |

**响应式表单：**
```css
.form-row {
  display: grid;
  gap: 16px;
  grid-template-columns: 1fr;
}

@media (min-width: 768px) {
  .form-row { grid-template-columns: 1fr 1fr; }
}
```

---

### Footer (页脚)

| 属性 | 375px | 768px | 1440px |
|------|-------|-------|--------|
| 列数 | 1 | 2-3 | 4-5 |
| 布局 | 垂直堆栈 | 网格 | 网格 + 侧栏 |
| 宽度 | 100% - 16px | 100% - 24px | max 1440px |
| Logo | 底部 | 左/上 | 左/上 |

---

## 文本响应式规则

| 元素 | 375px | 768px | 1440px |
|------|-------|-------|--------|
| H1 | 2.4rem | 3.2rem | 4rem |
| H2 | 1.8rem | 2.4rem | 3.2rem |
| H3 | 1.4rem | 1.8rem | 2.4rem |
| 正文 | 1rem | 1rem | 1.125rem |
| 行高 | 1.6 | 1.6 | 1.6-1.8 |
| 最大行宽 | 自动 | 60 字 | 75 字 (中文 36 字) |

**快速公式：** `font-size: clamp(1.4rem, 3vw, 2.4rem);`

---

## 图片响应式规则

| 情况 | 处理方式 | 代码 |
|------|---------|------|
| 固定宽高比 | srcset + picture | `<picture>` tag |
| 填充容器 | object-fit | `object-fit: cover;` |
| 懒加载 | loading="lazy" | `<img loading="lazy">` |
| Retina 屏 | 2x 图片 | srcset="img.jpg 1x, img@2x.jpg 2x" |

---

## 断点 Media Query 速查

```css
/* 375px+ (手机) */
@media (min-width: 375px) { ... }

/* 600px+ (大手机) */
@media (min-width: 600px) { ... }

/* 768px+ (平板) */
@media (min-width: 768px) { ... }

/* 1024px+ (小笔记本) */
@media (min-width: 1024px) { ... }

/* 1440px+ (桌面) */
@media (min-width: 1440px) { ... }

/* 1920px+ (大屏) */
@media (min-width: 1920px) { ... }

/* 仅限手机 (< 768px) */
@media (max-width: 767px) { ... }

/* 横屏检测 */
@media (orientation: landscape) { ... }
```

---

## 移动优先 vs 桌面优先

**推荐：移动优先**
```css
/* 基础 (手机) */
.card { grid-template-columns: 1fr; }

/* 升级到平板 */
@media (min-width: 768px) { grid-template-columns: repeat(2, 1fr); }

/* 升级到桌面 */
@media (min-width: 1440px) { grid-template-columns: repeat(3, 1fr); }
```

---

## 交互响应式规则

| 交互 | 手机 (375px) | 平板 (768px) | 桌面 (1440px) |
|------|-------------|-------------|-------------|
| 按钮大小 | 44px+ (触摸) | 40px+ | 36px+ |
| 触摸间距 | 8px+ | 8px | 4px+ |
| 下拉菜单 | 模态/全屏 | 下拉 | 下拉 |
| 悬停 | 无 (tap 代替) | 可用 | 完整悬停效果 |
| 手指友好 | 是 | 是 | 指针优化 |

---

## 更新历史

| 日期 | 变更 | 说明 |
|------|------|------|
| 2026-08-29 | 初稿 | 创建响应式决策矩阵 |
