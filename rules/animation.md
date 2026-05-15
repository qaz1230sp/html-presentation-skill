# Animation & Visual Dynamics / 动画与视觉动效规则

This file governs how animations, fragments, and visual effects are applied. Read it after `composition.md` and before writing HTML. Its purpose: make presentations feel alive, cinematic, and anti-generic — not like a default PowerPoint or AI-generated artifact.

## Core Philosophy: 演的不是动画，是信息

动画的存在意义不是"让页面动起来"，而是**帮观众理解信息的结构和关系**。每一个动效都应该回答一个问题：**这个动画让观众更容易理解了什么？**

如果答案是"什么都没有，只是好看"——删掉它。

---

## 三大原则

### 原则 1: 内容决定动画，不是动画装饰内容

| 信息关系 | 推荐动效 | 错误做法 |
|----------|----------|----------|
| 递进/顺序 | 从左到右依次滑入，或从下往上逐级抬升 | 全部同时 fade-in |
| 对比/冲突 | 两侧同时从对向入场，或一侧先出、另一侧反向覆盖 | 两边都 fade-in |
| 因果/转化 | A 先出现 → 连接线/箭头绘制 → B 出现 | A 和 B 一起 fade-in |
| 强调/高亮 | scale pulse、背景色闪烁、边框亮起 | 加粗加下划线 |
| 聚合/归纳 | 散落元素向中心聚拢，或列表项收缩为一个总结 | 直接切到总结页 |
| 时间线/流程 | 节点沿轨道依次点亮，连线逐段绘制 | 所有节点同时出现 |

### 原则 2: 相邻 slides 的主导动画必须不同

连续三页使用同一种入场方式（如全部 fade-up）= 视觉疲劳。**相邻页的主导过渡效果必须有变化**。

变化维度（任选其一即可）：
- 方向不同（左入 → 下入 → 右入）
- 类型不同（滑动 → 缩放 → 渐显 → 翻转）
- 节奏不同（快闪入 → 慢浮现）

### 原则 3: 每套 PPT 至少有一处"表演性动画"

所谓"表演性动画"是指不只是让元素出现/消失，而是**用动画本身在讲解一个概念**：
- 数字从 0 滚动到目标值
- 进度条从空到满
- 流程图节点依次点亮并连线
- 代码逐行高亮（打字机效果）
- 对比数据用天平/杠杆可视化

这类动画至少出现 **1 次**。8 页以上的 deck 建议 **2-3 次**。

---

## Fragment 进阶用法（reveal.js 原生能力）

基础的 `class="fragment"` 只是 fade-in。reveal.js 支持以下变体，**必须混合使用**：

| Fragment 类型 | CSS class | 适用场景 |
|--------------|-----------|----------|
| 渐显 | `fragment fade-in` | 通用补充信息 |
| 上浮渐显 | `fragment fade-up` | 列表递进 |
| 左滑入 | `fragment fade-left` | 对比中的右列 |
| 右滑入 | `fragment fade-right` | 对比中的左列 |
| 缩放弹入 | `fragment zoom-in` | 强调核心数据 |
| 先隐后显（配合退场） | `fragment fade-in-then-semi-out` | 逐步聚焦，前项灰化 |
| 高亮 | `fragment highlight-current-blue` | 当前讨论项 |
| 缩小退场 | `fragment shrink` | 被替代的旧方案 |

**规则：同一页内如果有 2+ fragments，至少使用 2 种不同类型。**

**首项可见规则：列表/卡片/双栏等有多个条目的 slide，第一个条目必须在页面进入时直接可见（不加 fragment class）。只有第 2 项起才用 fragment。** 这保证页面进入时不是空白的——观众一眼就能看到主题内容。

---

## 自定义 CSS 动画工具箱

以下动画可以直接在 `<style>` 中定义。用 `data-fragment-index` 配合 `.visible` 状态触发：

### 数字滚动（Counter Roll）
```css
@keyframes countUp {
  from { --num: 0; }
  to { --num: var(--target); }
}
.stat-num {
  animation: countUp 1.5s ease-out forwards;
  counter-reset: num var(--num);
  font-variant-numeric: tabular-nums;
}
.stat-num::after {
  content: counter(num);
}
```

### 描边绘制（Stroke Draw）
```css
@keyframes drawLine {
  to { stroke-dashoffset: 0; }
}
.draw-path {
  stroke-dasharray: var(--path-length);
  stroke-dashoffset: var(--path-length);
  animation: drawLine 1.2s ease-in-out forwards;
  animation-play-state: paused;
}
.fragment.visible .draw-path {
  animation-play-state: running;
}
```

### 进度条填充（Bar Fill）
```css
@keyframes fillBar {
  from { width: 0; }
  to { width: var(--fill-pct); }
}
.progress-fill {
  animation: fillBar 1s cubic-bezier(0.4, 0, 0.2, 1) forwards;
  animation-play-state: paused;
}
.fragment.visible .progress-fill {
  animation-play-state: running;
}
```

### 打字机效果（Typewriter）

基础内联打字效果，适合单行文字强调：

```css
@keyframes typing {
  from { width: 0; }
  to { width: 100%; }
}
.typewriter {
  overflow: hidden;
  white-space: nowrap;
  border-right: 2px solid var(--accent-primary, #667eea);
  animation: typing 2s steps(var(--chars), end) forwards,
             blink 0.6s step-end infinite alternate;
  animation-play-state: paused;
  width: 0;
}
@keyframes blink {
  50% { border-color: transparent; }
}
.fragment.visible .typewriter {
  animation-play-state: running;
}
```

#### 终端打字机（Terminal Typewriter）

当内容是 CLI 命令或终端交互时，使用完整终端组件而非简单打字效果。
完整的终端窗口模板、CSS 和使用规则见 `layouts/terminal-demo.md`。

核心技术组合：
1. **终端外壳** — 圆角窗口 + 三色圆点装饰条（macOS 风格）
2. **逐字输入** — `width: 0 → Nch`，`steps(N, end)` 精确匹配字符数
3. **块状光标** — `background` 色块 + `step-end` 闪烁（比 `border-right` 更像真实终端）
4. **输出逐行浮现** — `opacity: 0; translateY(14px)` + 递增 `animation-delay`
5. **侧边命令卡** — 从下方滑入，展示相关命令

何时使用终端布局 vs 内联打字效果：
- **终端布局**：完整命令 + 执行结果场景（安装、部署、构建）
- **内联打字**：标题或关键词的单行强调效果

### 脉冲强调（Pulse Highlight）
```css
@keyframes pulse {
  0%, 100% { transform: scale(1); box-shadow: 0 0 0 0 var(--accent-primary, rgba(102,126,234,0.4)); }
  50% { transform: scale(1.05); box-shadow: 0 0 0 12px transparent; }
}
.pulse-highlight {
  animation: pulse 1.5s ease-in-out 2;
}
```

---

## Slide Transition 多样化

reveal.js 支持 per-slide transition override。**禁止全 deck 使用同一种 transition。**

```html
<!-- 在需要变化的 section 上设置 -->
<section data-transition="zoom">      <!-- 强调：重要结论 -->
<section data-transition="convex">    <!-- 空间感：架构图 -->
<section data-transition="fade">      <!-- 平静：引言/引用 -->
<section data-transition="slide">     <!-- 默认：叙述推进 -->
<section data-transition="none">      <!-- 紧凑：代码前后对比 -->
```

### 使用规则

- 默认使用 config 设定的 transition（通常 `slide`）
- **强调页**（结论、金句、关键数据）：用 `zoom` 或 `convex` 突出
- **呼吸页**（引用、全图）：用 `fade` 柔和过渡
- **对比页**（before/after 紧挨）：用 `none` 消除过渡感
- 同一种非默认 transition 不得连续出现超过 2 次

---

## 反模式清单（Anti-Patterns）

以下是 AI 生成演示文稿的常见视觉指纹，**全部禁止**：

### 动画层面
| ❌ 禁止 | ✅ 替代方案 |
|---------|------------|
| 全场所有元素都用 fade-in | 根据信息关系选动画类型 |
| 所有 fragment 用相同的 `fade-up` | 混合 2+ 种 fragment 类型 |
| 装饰性的持续呼吸/脉冲动画（无功能意义） | 只在需要吸引注意力时短暂脉冲 |
| transition 全 deck 一个设置 | 关键页用不同 transition 制造节奏 |
| 动画时间全用 0.5s / 1s 整数 | 用 0.3s / 0.7s / 1.2s 等非整数制造自然感 |

### 视觉层面
| ❌ 禁止 | ✅ 替代方案 |
|---------|------------|
| 紫粉/蓝紫对角渐变做背景（AI 味极重） | 使用主题定义的背景 |
| 每页都有装饰性圆角卡片 + 彩色左边框 | 只在 card-grid 布局用卡片；边框用主题 accent |
| emoji 做图标 | 用 inline SVG 或无图标纯文字 |
| 渐变色按钮 + 大圆角药丸 | 扁平按钮或 ghost 按钮 |
| 所有页面用同一个装饰元素（如右上角圆点） | 装饰随布局变化，或去掉装饰 |
| 假数据、假 Logo、假"XX 万用户" | 用 placeholder 注明"待替换"或用真实数据 |

---

## SVG 与视觉演示（每 5 页建议出现 1 次）

对于 8+ 页的 deck，纯文字 + 图表容易单调。建议每 5 页插入一处**内联 SVG 或 CSS 视觉演示**：

### 适用场景

| 内容类型 | 推荐视觉手法 |
|----------|-------------|
| 架构/流程 | SVG 流程图 + 描边绘制动画 |
| 数据增长 | 进度条 / 柱状图 CSS 动画填充 |
| 对比数据 | 天平/跷跷板 SVG + 倾斜动画 |
| 时间线 | 轨道 + 节点逐个点亮 |
| 代码执行 | 终端样式 + 打字机逐行显示 |
| 多选项 | 卡片翻转 / 手风琴展开 |

### 实现约束

- SVG 必须内联（不用外部文件）
- 宽度设 `width="100%"`，高度设 `max-height` 约束
- 动画用 CSS 控制，不用 SMIL（兼容性更好）
- 配色引用主题 CSS 变量（如 `var(--accent-primary)`）

---

## 完整检查清单（补充 quality-checklist.md）

生成完成后额外检查：

- [ ] 相邻页面的主导动画/transition 不雷同
- [ ] 同一页内 2+ fragments 使用了至少 2 种不同类型
- [ ] 至少 1 处"表演性动画"（数字滚动/描边绘制/进度填充/打字机等）
- [ ] 无持续循环的纯装饰动画（无 `infinite` 关键帧，除打字机光标外）
- [ ] 动画时长使用非整数值（0.3s / 0.7s / 1.2s），避免机械感
- [ ] 无 AI 视觉指纹（无紫粉渐变/emoji 图标/假数据）
- [ ] 8+ 页 deck 至少有 1 处内联 SVG 或 CSS 视觉演示
- [ ] per-slide transition 至少有 2 种不同设定
- [ ] fragment 类型的选择与信息关系匹配（递进用 fade-up，对比用 fade-left/right 等）
