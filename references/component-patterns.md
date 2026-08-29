# Component Implementation Patterns

常用 UI 组件的快速实现模板，开即用。

## Button (按钮)

### HTML 结构

```html
<!-- 基础按钮 -->
<button class="btn btn-primary">Click me</button>

<!-- 按钮变体 -->
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-danger">Danger</button>
<button class="btn btn-disabled" disabled>Disabled</button>

<!-- 含 icon 按钮 -->
<button class="btn btn-primary">
  <svg class="icon">...</svg>
  <span>Label</span>
</button>

<!-- 仅 icon 按钮 -->
<button class="btn btn-icon" aria-label="Menu">
  <svg class="icon">...</svg>
</button>
```

### CSS

```css
.btn {
  display: inline-flex;
  align-items: center;
  gap: var(--spacing-sm);
  padding: var(--spacing-sm) var(--spacing-md);
  background: transparent;
  border: 1px solid transparent;
  border-radius: var(--border-radius-md);
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 300ms ease-in-out;
}

.btn:hover:not(:disabled) { transform: translateY(-2px); box-shadow: var(--shadow-md); }
.btn:active:not(:disabled) { transform: translateY(0); }
.btn:disabled { opacity: 0.6; cursor: not-allowed; }

/* 按钮类型 */
.btn-primary { background: var(--color-primary); color: white; }
.btn-primary:hover:not(:disabled) { background: var(--color-primary-dark); }

.btn-secondary { background: var(--color-bg-light); color: var(--color-primary); border: 1px solid var(--color-primary); }

.btn-danger { background: var(--color-error); color: white; }

.btn-icon { padding: var(--spacing-sm); border-radius: 50%; }
```

---

## Input Field (输入框)

### HTML

```html
<!-- 基础输入 -->
<div class="form-group">
  <label for="email">Email</label>
  <input type="email" id="email" placeholder="your@email.com" required>
</div>

<!-- 带错误 -->
<div class="form-group form-group--error">
  <label for="password">Password</label>
  <input type="password" id="password" aria-describedby="password-error" required>
  <span id="password-error" class="form-error" role="alert">至少 8 个字符</span>
</div>

<!-- 成功状态 -->
<div class="form-group form-group--success">
  <input type="text" placeholder="用户名">
  <span class="form-success">✓ 用户名可用</span>
</div>
```

### CSS

```css
.form-group {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-sm);
  margin-bottom: var(--spacing-md);
}

.form-group label {
  font-weight: 600;
  font-size: 0.875rem;
  color: var(--color-text-primary);
}

.form-group input {
  padding: var(--spacing-sm) var(--spacing-md);
  border: 1px solid var(--color-text-secondary);
  border-radius: var(--border-radius-md);
  font-size: 1rem;
  transition: border-color 300ms, box-shadow 300ms;
}

.form-group input:focus {
  outline: none;
  border-color: var(--color-primary);
  box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.1);
}

.form-group--error input {
  border-color: var(--color-error);
  background: rgba(220, 53, 69, 0.05);
}

.form-error, .form-success {
  font-size: 0.75rem;
  margin-top: -4px;
}

.form-error { color: var(--color-error); }
.form-success { color: var(--color-success); }
```

---

## Card (卡片)

### HTML

```html
<!-- 基础卡片 -->
<div class="card">
  <img src="image.jpg" alt="卡片图片" class="card-image">
  <div class="card-content">
    <h3 class="card-title">Card Title</h3>
    <p class="card-description">Card description text...</p>
    <button class="btn btn-primary">Action</button>
  </div>
</div>

<!-- 卡片组 (网格) -->
<div class="card-grid">
  <div class="card">...</div>
  <div class="card">...</div>
  <div class="card">...</div>
</div>
```

### CSS

```css
.card {
  background: var(--color-bg-light);
  border: 1px solid #e0e0e0;
  border-radius: var(--border-radius-md);
  overflow: hidden;
  transition: all 300ms ease-in-out;
}

.card:hover {
  box-shadow: var(--shadow-lg);
  transform: translateY(-4px);
}

.card-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card-content {
  padding: var(--spacing-md);
}

.card-title {
  margin: 0 0 var(--spacing-sm) 0;
  font-size: 1.2rem;
  font-weight: 600;
}

.card-description {
  margin: 0 0 var(--spacing-md) 0;
  color: var(--color-text-secondary);
  font-size: 0.9rem;
}

/* 卡片网格 */
.card-grid {
  display: grid;
  gap: var(--spacing-md);
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
}

@media (max-width: 768px) {
  .card-grid { grid-template-columns: 1fr; }
}
```

---

## Modal/Dialog (模态框)

### HTML

```html
<!-- 触发按钮 -->
<button class="btn btn-primary" data-modal-trigger="modalId">Open Modal</button>

<!-- 模态框 -->
<div id="modalId" class="modal" role="dialog" aria-labelledby="modalTitle">
  <div class="modal-overlay"></div>
  <div class="modal-content">
    <div class="modal-header">
      <h2 id="modalTitle">Modal Title</h2>
      <button class="modal-close" aria-label="关闭模态框">&times;</button>
    </div>
    <div class="modal-body">
      <p>Modal content goes here...</p>
    </div>
    <div class="modal-footer">
      <button class="btn btn-secondary" data-modal-close>Cancel</button>
      <button class="btn btn-primary" data-modal-close>Confirm</button>
    </div>
  </div>
</div>
```

### CSS

```css
.modal {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1000;
}

.modal.active {
  display: flex;
  align-items: center;
  justify-content: center;
  animation: fadeIn 300ms ease-in-out;
}

.modal-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(2px);
}

.modal-content {
  position: relative;
  z-index: 1001;
  background: var(--color-bg-light);
  border-radius: var(--border-radius-lg);
  box-shadow: var(--shadow-xl);
  width: 90%;
  max-width: 500px;
  animation: slideUp 300ms ease-in-out;
}

.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--spacing-lg);
  border-bottom: 1px solid #e0e0e0;
}

.modal-body {
  padding: var(--spacing-lg);
}

.modal-footer {
  display: flex;
  justify-content: flex-end;
  gap: var(--spacing-md);
  padding: var(--spacing-lg);
  border-top: 1px solid #e0e0e0;
}

.modal-close {
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  padding: 0;
}

@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
@keyframes slideUp { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
```

### JavaScript

```javascript
document.addEventListener('DOMContentLoaded', () => {
  const triggers = document.querySelectorAll('[data-modal-trigger]');
  const closeButtons = document.querySelectorAll('[data-modal-close]');
  
  triggers.forEach(btn => {
    btn.addEventListener('click', () => {
      const modalId = btn.dataset.modalTrigger;
      const modal = document.getElementById(modalId);
      modal.classList.add('active');
      document.body.style.overflow = 'hidden';
    });
  });
  
  closeButtons.forEach(btn => {
    btn.addEventListener('click', (e) => {
      const modal = e.target.closest('.modal');
      modal.classList.remove('active');
      document.body.style.overflow = 'auto';
    });
  });
  
  document.querySelectorAll('.modal-overlay').forEach(overlay => {
    overlay.addEventListener('click', (e) => {
      e.target.closest('.modal').classList.remove('active');
      document.body.style.overflow = 'auto';
    });
  });
});
```

---

## Navigation (导航栏)

### HTML

```html
<nav class="navbar">
  <div class="navbar-container">
    <a href="/" class="navbar-logo">Logo</a>
    
    <button class="navbar-toggle" aria-label="Toggle navigation" aria-expanded="false">
      <span></span>
      <span></span>
      <span></span>
    </button>
    
    <ul class="navbar-menu">
      <li><a href="/">Home</a></li>
      <li><a href="/about">About</a></li>
      <li><a href="/services">Services</a></li>
      <li><a href="/contact" class="btn btn-primary">Contact</a></li>
    </ul>
  </div>
</nav>
```

### CSS

```css
.navbar {
  background: white;
  border-bottom: 1px solid #e0e0e0;
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.navbar-container {
  max-width: 1440px;
  margin: 0 auto;
  padding: 0 var(--spacing-md);
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 60px;
}

.navbar-logo {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--color-primary);
  text-decoration: none;
}

.navbar-menu {
  display: flex;
  list-style: none;
  gap: var(--spacing-lg);
  margin: 0;
  padding: 0;
}

.navbar-menu a {
  text-decoration: none;
  color: var(--color-text-primary);
  font-weight: 500;
  transition: color 300ms;
}

.navbar-menu a:hover {
  color: var(--color-primary);
}

/* 汉堡菜单 (手机) */
.navbar-toggle {
  display: none;
  flex-direction: column;
  background: none;
  border: none;
  cursor: pointer;
  gap: 4px;
}

.navbar-toggle span {
  width: 24px;
  height: 2px;
  background: var(--color-text-primary);
  transition: all 300ms;
}

@media (max-width: 768px) {
  .navbar-toggle { display: flex; }
  
  .navbar-toggle.active span:nth-child(1) { transform: rotate(45deg) translateY(8px); }
  .navbar-toggle.active span:nth-child(2) { opacity: 0; }
  .navbar-toggle.active span:nth-child(3) { transform: rotate(-45deg) translateY(-8px); }
  
  .navbar-menu {
    position: absolute;
    top: 60px;
    left: 0;
    right: 0;
    flex-direction: column;
    background: white;
    border-bottom: 1px solid #e0e0e0;
    padding: var(--spacing-md);
    gap: 0;
    max-height: 0;
    overflow: hidden;
    transition: max-height 300ms ease-in-out;
  }
  
  .navbar-menu.active {
    max-height: 300px;
  }
  
  .navbar-menu li {
    border-bottom: 1px solid #f0f0f0;
    padding: var(--spacing-md) 0;
  }
}
```

### JavaScript

```javascript
const toggle = document.querySelector('.navbar-toggle');
const menu = document.querySelector('.navbar-menu');

toggle.addEventListener('click', () => {
  toggle.classList.toggle('active');
  menu.classList.toggle('active');
  toggle.setAttribute('aria-expanded', toggle.classList.contains('active'));
});
```

---

## 无障碍标记最小集 (Accessibility)

```html
<!-- 按钮 aria-label -->
<button aria-label="关闭菜单">✕</button>

<!-- 图片 alt 文本 -->
<img src="hero.jpg" alt="产品展示图片">

<!-- 链接 title 属性 -->
<a href="/page" title="导航到页面">More</a>

<!-- 表单验证 aria-describedby -->
<input aria-describedby="error-msg" required>
<span id="error-msg" role="alert">必填字段</span>

<!-- 动态更新 aria-live -->
<div aria-live="polite" aria-atomic="true">
  Products added: 3
</div>

<!-- 模态 role="dialog" -->
<div role="dialog" aria-labelledby="title">...</div>

<!-- 复选框 aria-checked -->
<input type="checkbox" aria-checked="false">

<!-- 加载中 aria-busy -->
<div aria-busy="true">Loading...</div>
```

---

## 常见 Bug 与修复

| 问题 | 原因 | 修复 |
|------|------|------|
| z-index 不起效 | 上级元素 position 改变堆叠顺序 | 检查父元素 position, 调整 z-index |
| Flexbox 收缩 | flex-shrink 默认 1 | 加 flex-shrink: 0 或 flex: 0 0 auto |
| 输入框 padding 显示异常 | box-sizing: content-box | 全局设 box-sizing: border-box |
| 移动端点击延迟 | 触发事件延迟 | 用 touch 事件或 pointer-events: auto |
| 字体闪烁 (FOUT) | 字体加载慢 | 用 font-display: swap |

---

## 更新历史

| 日期 | 变更 | 说明 |
|------|------|------|
| 2026-08-29 | 初稿 | 创建通用组件实现模板 |
