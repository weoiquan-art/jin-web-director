# Design System Reference

快速查表式设计系统参考，最小化 token 消耗。

## 色彩 (Colors)

| 用途 | 变量名 | HEX | RGB | 用在 |
|------|--------|-----|-----|------|
| primary | `--color-primary` | 待定 | 待定 | CTA, 活跃状态, 强调 |
| secondary | `--color-secondary` | 待定 | 待定 | 次要动作, 链接 |
| success | `--color-success` | 待定 | 待定 | 成功提示, ✓ 状态 |
| error | `--color-error` | 待定 | 待定 | 错误提示, 删除按钮 |
| warning | `--color-warning` | 待定 | 待定 | 警告提示, 注意 |
| info | `--color-info` | 待定 | 待定 | 信息提示 |
| bg-light | `--color-bg-light` | 待定 | 待定 | 页面背景, 浅卡片 |
| bg-dark | `--color-bg-dark` | 待定 | 待定 | 深色背景, 对比 |
| text-primary | `--color-text-primary` | 待定 | 待定 | 正文, 标题 |
| text-secondary | `--color-text-secondary` | 待定 | 待定 | 辅助文本, 标签 |

**使用方式：** `color: var(--color-primary);`

---

## 排版 (Typography)

| 用途 | 字体 | 大小 | 权重 | 行高 | 字距 |
|------|------|------|------|------|------|
| H1 | 待定 | 3.2rem | 700 | 1.2 | normal |
| H2 | 待定 | 2.4rem | 700 | 1.3 | normal |
| H3 | 待定 | 1.8rem | 600 | 1.4 | normal |
| H4 | 待定 | 1.4rem | 600 | 1.5 | normal |
| body | 待定 | 1rem | 400 | 1.6 | normal |
| body-sm | 待定 | 0.875rem | 400 | 1.6 | normal |
| caption | 待定 | 0.75rem | 500 | 1.4 | 0.5px |

**使用方式：** 在 CSS 中定义 `--font-family`, `--font-size-*`, `--font-weight-*`

---

## 间距系统 (Spacing Scale)

| 名称 | px | rem | 用在 |
|------|-----|-----|------|
| xs | 4px | 0.25rem | icon spacing, 细节间距 |
| sm | 8px | 0.5rem | 紧凑 padding, 小元素 |
| md | 16px | 1rem | 默认 padding, 标准间距 |
| lg | 24px | 1.5rem | 块级间距, 卡片内间距 |
| xl | 32px | 2rem | 大块间距, section padding |
| 2xl | 48px | 3rem | hero padding, 主要分隔 |
| 3xl | 64px | 4rem | page padding, 大分隔 |

**快速用法：** `padding: var(--spacing-md); margin: var(--spacing-lg);`

---

## 圆角 (Border Radius)

| 用途 | px | 用在 |
|------|-----|------|
| none | 0 | 严格直角 |
| sm | 4px | 表单输入, 小按钮 |
| md | 8px | 默认卡片, 标准按钮 |
| lg | 12px | 大卡片, 模态框 |
| full | 9999px | 圆形头像, 药丸按钮 |

---

## 阴影 (Shadows)

| 等级 | CSS | 用在 |
|------|-----|------|
| shadow-sm | `0 1px 2px rgba(0,0,0,0.05)` | 微妙分层 |
| shadow-md | `0 4px 6px rgba(0,0,0,0.1)` | 默认卡片 |
| shadow-lg | `0 10px 15px rgba(0,0,0,0.1)` | 浮动元素, 模态 |
| shadow-xl | `0 20px 25px rgba(0,0,0,0.1)` | 下拉菜单, 顶层 |

---

## 断点 (Breakpoints)

| 名称 | 宽度 | 设备 | 栅格列 |
|------|------|------|--------|
| xs | 375px | 手机 | 1-2 |
| sm | 600px | 大手机 | 2 |
| md | 768px | 平板 | 3-4 |
| lg | 1024px | 小笔记本 | 4-6 |
| xl | 1440px | 桌面 | 6-12 |
| 2xl | 1920px | 大屏 | 12 |

---

## 过渡与动画 (Transitions)

| 类型 | 时间 | 速率 | 用在 |
|------|------|------|------|
| 快速 | 150ms | ease-in-out | hover 状态 |
| 标准 | 300ms | ease-in-out | 默认动画 |
| 慢速 | 500ms | ease-out | 复杂动画, 页面转换 |

**缓动函数：** `transition: all 300ms ease-in-out;`

---

## 组件色彩应用

### Button
- **primary (默认)：** bg=primary, text=white, hover=primary-dark
- **secondary：** bg=bg-light, text=primary, border=primary
- **danger：** bg=error, text=white, hover=error-dark
- **disabled：** bg=gray-300, text=gray-500, cursor=not-allowed

### Input
- **边框：** color-text-secondary (1px)
- **焦点：** border=primary, box-shadow=primary (透明 20%)
- **错误：** border=error, bg=error (透明 5%)

### Card
- **bg：** color-bg-light
- **边框：** color-text-secondary (1px)
- **阴影：** shadow-md

---

## 快速复制模板

```css
/* CSS 变量声明 */
:root {
  --color-primary: #007BFF;
  --color-text-primary: #1F2937;
  --spacing-md: 1rem;
  --font-size-body: 1rem;
  --shadow-md: 0 4px 6px rgba(0,0,0,0.1);
}

/* 常见使用 */
button {
  background: var(--color-primary);
  padding: var(--spacing-md);
  border-radius: var(--border-radius-md);
  box-shadow: var(--shadow-md);
}
```

---

## 更新历史

| 日期 | 变更 | 说明 |
|------|------|------|
| 2026-08-29 | 初稿 | 创建系统参考表 |

**注：** 具体值待从项目设计稿或现有代码提取。
