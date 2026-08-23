# JIN Web Director

一个面向 Codex / Agent 的个人网站搭建 Skill：让网站工作先经过产品判断、信息架构、视觉方向、响应式、工程实现、QA 与部署验证，再进入代码。

它不是模板库，也不复制第三方 Skill；它把 JIN 已验证的网站实践与公开方法论整理成可执行的规则。

## 适用场景

- 从零建立作品集、课程页、服务页、商家获客页或内容网站；
- 在现有 React + Vite 或其他网站项目中改版、补移动端、优化互动或审查 UI；
- 设计和技术 QA、构建、部署、交接与持续维护；
- 为真实项目建立 `PRODUCT.md`、`DESIGN.md`、`DEPLOY.md` 与 `CHANGELOG.md`。

## 使用方式

将整个 `jin-web-director` 目录放入 Codex 的 skills 目录，或将它放到具体项目的 agent-skills 目录。然后在网站任务中引用 `$jin-web-director`，或让项目 `AGENTS.md` 指向本 Skill。

首次处理已有网站时，先让 Agent 检查项目结构并复述理解；不要直接要求“重做整个网站”。

## 目录

```text
jin-web-director/
├── SKILL.md
├── AGENTS.md
├── README.md
├── project-memory.md
├── agents/
│   └── openai.yaml
├── principles/
│   ├── product-design.md
│   ├── visual-taste.md
│   ├── interaction-direction.md
│   ├── responsive-design.md
│   └── accessibility.md
├── workflows/
│   ├── codebase-inspection.md
│   ├── new-site-workflow.md
│   ├── redesign-workflow.md
│   ├── agent-development-workflow.md
│   └── deployment.md
├── quality/
│   ├── interface-quality.md
│   ├── qa-checklist.md
│   ├── performance.md
│   └── seo.md
├── references/
│   ├── external-skills.md
│   └── lessons-learned.md
└── source-material/
    ├── JIN_网站搭建方法论_弯路与技巧复盘_v1.0.docx
    └── 網站搭建方法論.md
```

`source-material/` 保留原始两份资料；运行时优先读取 `SKILL.md` 和按需链接的细分文件，不需要每次加载原稿。

## 核心立场

1. 先定义网站任务，再设计页面。
2. 先审计现有项目，再修改代码。
3. 先让静态层级成立，再添加动效。
4. 桌面与移动端同步设计。
5. Git 仓库是源码的单一真相来源；构建产物、托管平台和域名分别管理。
6. 用真实内容和真实验证交付，不用虚假数据、案例或“应该可以”的假设。

## 来源与维护

外部方法只做归纳吸收，详见 [references/external-skills.md](references/external-skills.md)。真实项目经验记录在 [references/lessons-learned.md](references/lessons-learned.md)，每新增一条都应附带日期、证据和预防规则。
