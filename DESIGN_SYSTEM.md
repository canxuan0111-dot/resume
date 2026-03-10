# 设计规范 · Design System

> 基于首页 (`src/pages/index.astro`) 和全局布局 (`src/layouts/Layout.astro`) 沉淀，适用于本站所有页面。

---

## 一、色彩系统 Color Tokens

所有颜色通过 CSS 变量定义在 `:root`，使用时直接引用变量名。

### 背景色

| 变量 | 值 | 用途 |
|------|-----|------|
| `--bg` | `#ffffff` | 主背景（奇数楼层） |
| `--bg-alt` | `#f0f0f0` | 次背景（偶数楼层，区分节奏） |
| `--surface` | `#f7f7f5` | 卡片内浅灰底面 |
| `--canvas-dark` | `#0a0a0a` | 深色全屏背景（如项目 Hero） |

### 文字色

| 变量 | 值 | 用途 |
|------|-----|------|
| `--text` | `#0a0a0a` | 主文字（亮色背景上） |
| `--text-inv` | `#ffffff` | 反色文字（深色背景上） |
| `--muted` | `rgba(10,10,10,0.45)` | 辅助文字、日期、描述 |
| `--muted-inv` | `rgba(255,255,255,0.45)` | 深色背景上的辅助文字 |

### 品牌色 / 强调色

| 变量 | 值 | 用途 |
|------|-----|------|
| `--accent` | `#0062ff` | 品牌蓝，eyebrow 标签、链接高亮 |
| `--accent-bg` | `rgba(0,98,255,0.07)` | 蓝色浅底 |
| `--accent-border` | `rgba(0,98,255,0.2)` | 蓝色边框 |
| `--red` | `#f9442c` | CTA 圆圈箭头、强调红 |

### 语义色（指标/状态）

| 变量 | 值 | 用途 |
|------|-----|------|
| `--green` | `#00a854` | 正向指标文字 |
| `--green-bg` | `rgba(0,168,84,0.07)` | 指标卡浅绿底 |
| `--green-border` | `rgba(0,168,84,0.2)` | 指标卡绿色边框 |
| `--amber` | `#d97706` | 警示/次要状态 |
| `--amber-bg` | `rgba(217,119,6,0.07)` | 警示浅底 |
| `--amber-border` | `rgba(217,119,6,0.2)` | 警示边框 |

### 边框

| 变量 | 值 | 用途 |
|------|-----|------|
| `--border` | `rgba(0,0,0,0.08)` | 常规分割线、卡片边框 |
| `--border-mid` | `rgba(0,0,0,0.13)` | 稍重边框（技能标签等） |
| `--border-inv` | `rgba(255,255,255,0.1)` | 深色背景上的边框 |

---

## 二、字体系统 Typography

### 字体族

| 变量 | 字体 | 用途 |
|------|------|------|
| `--font-display` | `'Syne', sans-serif` | 展示/标题字体，几何无衬线 |
| `--font-sans` | `'Inter', -apple-system, "PingFang SC", ...` | 正文字体，中英混排 |

> 字体通过 Google Fonts 加载：`Inter`（400/500/600/700）和 `Syne`（400/500/600/700/800）。

### 标题规格

| 级别 | 字体 | 字号 | 字重 | 字间距 | 行高 |
|------|------|------|------|--------|------|
| 超大展示（Hero 名字） | Syne | `clamp(64px, 14vw, 200px)` | 400 | `-0.04em` | `0.9` |
| 大标题（楼层 h2） | Syne | `clamp(36px, 5vw, 64px)` | 400 | `-0.04em` | `1.08` |
| 楼层标题（bold） | Syne | `clamp(36px, 5vw, 56px)` | 700 | `-0.03em` | `1.08` |
| 中标题（卡片 h3） | Syne | `22px` | 600 | `-0.02em` | `1.25` |

### 正文规格

| 用途 | 字体 | 字号 | 字重 | 行高 | 颜色 |
|------|------|------|------|------|------|
| 大段引言/描述 | Syne | `clamp(22px, 2.8vw, 38px)` | 400 | `1.45` | `--text` |
| 正文段落 | Inter | `16px` | 400 | `1.8` | `rgba(10,10,10,0.72)` |
| 正文小字 | Inter | `13.5px` | 400 | `1.75` | `rgba(10,10,10,0.55)` |
| Eyebrow 标签 | Inter | `11.5px` | 600 | — | `--accent` |
| 元数据（日期等） | Inter | `11.5px` | 500 | — | `--muted` |

---

## 三、间距系统 Spacing

### 间距变量

| 变量 | 值 | 典型用途 |
|------|-----|---------|
| `--sp-xs` | `8px` | 元素内小间距 |
| `--sp-sm` | `16px` | 紧凑行间距 |
| `--sp-md` | `32px` | 段落间距 |
| `--sp-lg` | `64px` | 区块间距 |
| `--sp-xl` | `120px` | 楼层上下内边距 |

### 楼层节奏

- 标准楼层：`padding: 100px 0`（上下）
- 内容容器：`max-width: 1080px; margin: 0 auto; padding: 0 40px`（左右）
- 移动端：内容区缩减为 `padding: 0 20px`，楼层上下缩为 `80px`

---

## 四、圆角系统 Border Radius

| 变量 | 值 | 用途 |
|------|-----|------|
| `--radius` | `12px` | 普通卡片、输入框 |
| `--radius-lg` | `20px` | 大卡片、图片容器 |
| `--radius-pill` | `100px` | 胶囊按钮、标签 |

---

## 五、阴影 Shadows

项目未使用变量封装，直接使用以下规范值：

| 场景 | 值 |
|------|----|
| 卡片悬停 | `0 16px 40px rgba(0,0,0,0.09)` |
| 导航胶囊 | `0 2px 24px rgba(0,0,0,0.14)` |
| Modal 弹窗 | `0 24px 80px rgba(0,0,0,0.15)` |

---

## 六、可复用组件 Components

所有组件位于 `src/components/`，在 `.astro` 文件中通过 `import` 引入使用。

---

### `CtaButton.astro` — 胶囊型 CTA 按钮

带红圆圈 `→` 图标，hover 时圆圈旋转 45° 弹簧弹出。

```astro
import CtaButton from '../components/CtaButton.astro';

// 基础用法（深色底，中号）
<CtaButton href="/resume" label="查看简历" />

// 浅色变体（用于 Hero 深色背景上）
<CtaButton href="/contact" label="联系我" variant="light" />

// 小尺寸（用于内联场景）
<CtaButton href="/articles" label="查看全部文章" size="sm" />
```

| Prop | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `href` | `string` | 必填 | 跳转链接 |
| `label` | `string` | 必填 | 按钮文字 |
| `variant` | `'dark' \| 'light'` | `'dark'` | 深色底白字 / 白底毛玻璃 |
| `size` | `'md' \| 'sm'` | `'md'` | 圆圈 36px / 30px |
| `class` | `string` | `''` | 透传额外 class |

---

### `SectionHeader.astro` — 楼层标题区

统一管理楼层的 eyebrow + 主标题 + 副标题，内置 reveal 动画。

```astro
import SectionHeader from '../components/SectionHeader.astro';

// 标准用法
<SectionHeader
  eyebrow="精选项目"
  title="将 AI 落地，<br>从 0 到 1"
  subtitle="每个项目都是完整的交付。"
/>

// 居中 + editorial 轻盈风（适合引言楼层）
<SectionHeader
  title="这是我 6 年来一直在做的事"
  weight="editorial"
  align="center"
/>

// 深色背景楼层（白色文字）
<SectionHeader
  eyebrow="工作方法"
  title="我的工作流程"
  theme="dark"
/>
```

| Prop | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `eyebrow` | `string` | — | 顶部蓝色小标签（可选） |
| `title` | `string` | 必填 | 主标题，支持 HTML（换行用 `<br>`） |
| `subtitle` | `string` | — | 副标题/描述（可选） |
| `weight` | `'editorial' \| 'bold'` | `'bold'` | 字重风格 |
| `align` | `'left' \| 'center'` | `'left'` | 对齐方式 |
| `theme` | `'light' \| 'dark'` | `'light'` | 亮色/深色背景适配 |
| `reveal` | `boolean` | `true` | 是否启用滚动入场动画 |

---

### `Tag.astro` — 标签/徽章

四种视觉变体，覆盖页面各使用场景。

```astro
import Tag from '../components/Tag.astro';

<Tag label="AI 产品设计" />                    // 默认 skill 风格
<Tag label="React" variant="tech" />           // 技术栈标签
<Tag label="AI SaaS · 小红书投放" variant="hero" />  // 项目 Hero 区
<Tag label="+35% 转化率" variant="metric" />   // 数据指标
```

| Prop | 类型 | 默认值 | 视觉 |
|------|------|--------|------|
| `label` | `string` | 必填 | 显示文字 |
| `variant` | `'skill' \| 'hero' \| 'tech' \| 'metric'` | `'skill'` | 见下表 |

| variant | 背景 | 边框 | 字色 | 用途 |
|---------|------|------|------|------|
| `skill` | `--bg` 白 | `--border-mid` | `rgba(10,10,10,0.7)` | 技能标签云（胶囊） |
| `hero` | 透明 | `rgba(255,255,255,0.15)` | `rgba(255,255,255,0.5)` | 深色 Hero 区分类标签 |
| `tech` | `--surface` 浅灰 | `--border` | `--muted` | 技术栈（小圆角方形） |
| `metric` | `--green-bg` | `--green-border` | `--green` | 数据正向指标 |

---

### `ArticleCard.astro` — 文章卡片

用于文章列表页和首页 Latest Insights 网格。

```astro
import ArticleCard from '../components/ArticleCard.astro';

<ArticleCard
  href="/articles/agent-architecture"
  title="Agent 产品架构工程化深度落地指南"
  date="2026-03"
  readTime="15 min"
  coverStyle="background: linear-gradient(135deg, #0a0a0a 0%, #0062ff 100%)"
/>

// 即将上线（降透明度）
<ArticleCard
  href="#"
  title="即将发布的文章"
  date="2026-04"
  readTime="8 min"
  soon={true}
/>
```

| Prop | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `href` | `string` | 必填 | 文章链接 |
| `title` | `string` | 必填 | 文章标题 |
| `date` | `string` | 必填 | 日期字符串（如 `"2026-03"`） |
| `readTime` | `string` | 必填 | 阅读时长（如 `"15 min"`） |
| `coverStyle` | `string` | `'background: #f0f0f0'` | 封面背景 CSS inline style |
| `soon` | `boolean` | `false` | 即将上线，降至 72% 透明度 |

#### 封面渐变参考

```css
/* 文章卡片封面渐变参考（可直接复制到 coverStyle） */
"background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 40%, #0062ff 100%)"  /* 深蓝 */
"background: linear-gradient(135deg, #0f2027 0%, #203a43 50%, #2c5364 100%)"  /* 深青 */
"background: linear-gradient(135deg, #1a0533 0%, #6b21a8 60%, #f9442c 100%)"  /* 紫红 */
```

---

## 七、动效规范 Motion

### 入场动画（Scroll Reveal）

全局在 `Layout.astro` 中通过 `IntersectionObserver` 实现。

```html
<!-- 给元素加 reveal class 即可触发滚动入场 -->
<div class="reveal">内容</div>

<!-- 配合延迟阶梯（0.08s 步进）-->
<div class="reveal reveal-delay-1">先出现</div>
<div class="reveal reveal-delay-2">后出现</div>
<div class="reveal reveal-delay-3">最后出现</div>
<!-- delay-1 至 delay-6，最大延迟 0.48s -->
```

动画参数：`opacity 0→1` + `translateY 32px→0`，时长 `0.7s`，缓动 `cubic-bezier(.25,.46,.45,.94)`

### 过渡缓动参考

| 场景 | 缓动曲线 | 时长 |
|------|---------|------|
| 常规 hover（透明度/位移） | `ease` / `0.2s~0.25s` | 快速响应 |
| 卡片上浮 | `cubic-bezier(.25,.46,.45,.94)` | `0.28s` |
| 弹簧弹出（圆圈旋转/缩放） | `cubic-bezier(0.34, 1.56, 0.64, 1)` | `0.3s` |
| 导航栏展/收 | `cubic-bezier(.4,0,.2,1)` | `0.42s~0.46s` |
| 入场动画 | `cubic-bezier(.25,.46,.45,.94)` | `0.7s~0.8s` |

---

## 八、导航栏规范 Navbar

### 两种模式

| 模式 | 触发方式 | 外观 |
|------|---------|------|
| **标准模式** | `navPill={false}`（默认） | 全宽横条，毛玻璃白底，logo + 右侧链接 |
| **胶囊模式** | `navPill={true}`（首页专用） | 居中悬浮胶囊，无 logo，仅导航链接 |

### 滚动行为

- 向下滚动 > 90px：导航收缩（标准模式滑出屏外，胶囊模式压缩为圆点）
- 向上滚动：导航展开恢复
- Hero 区内：胶囊模式保持白底（防止透明失效）

### 在 Layout 中使用

```astro
// 首页（胶囊）
<Layout title="首页" navPill={true}>

// 其他页面（标准）
<Layout title="简历">
```

---

## 九、响应式断点 Breakpoints

| 断点 | 主要变化 |
|------|---------|
| `≤ 900px` | 双列布局改为单列（About、Why Me），文章网格 3→2 列 |
| `≤ 768px` | 移动端导航隐藏链接，section 内边距缩减，文章网格 2→1 列 |
| `≤ 480px` | Hero 大字缩小，隐藏 tagline 和滚动指示器，极小字体优化 |

---

## 十、楼层背景交替规律

各楼层背景色按以下规律交替，保持视觉节奏：

```
Hero        → 全屏背景图（深色）
About       → --bg（白）
Selected Work → --bg-alt（浅灰）
Why Choose Me → --bg（白）
装饰图       → 全屏图片
My Process  → --bg（白）
Latest Insights → --bg-alt（浅灰）
```

---

*最后更新：2026-03-10*
