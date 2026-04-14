# 📖 Design Specification: Antique Vellum & Watercolor Jewel

A reading-first visual system for Obsidian.
This document describes the design logic of the **current shipped presets**, not an abstract target state.

## At a Glance

The implementation is built around three goals:

- **Make the screen feel less like glass, more like paper.**
- **Use color to organize information, not to demand attention.**
- **Reduce visual fatigue during long sessions.**

In the current project, that translates into:

- a warm multi-step vellum light palette
- soft graphite text
- restrained Prussian Blue structural accents
- watercolor-style rainbow categorization inside AnuPpuccin
- a shared reading-surface layer applied by the preset-specific CSS snippets

---

## 1. Core Visual Direction

This system intentionally avoids two common extremes in note-taking themes:

- high-contrast, high-saturation “cyberpunk” styling
- overly sterile, glassy minimalism

The shipped presets aim for calm concentration rather than visual intensity.

### Key principles

- **Physical metaphor** — The UI should feel closer to a warm paper workspace than a luminous slab of glass.
- **Restrained hierarchy** — Color is used mainly as a structural cue for files, headings, borders, and emphasis.
- **Anti-fatigue first** — The presets avoid pure black body text and hard white-black contrast in the light theme.

---

## 2. Material System

The current implementation does not use a single flat parchment color. Instead, it ships a **vellum palette family** layered across the light theme surface variables.

### 2.1 Light-mode vellum palette

The shipped presets currently override AnuPpuccin's light palette with these core background values:

- **Base:** `#EADFD3`
- **Mantle:** `#E2D4C4`
- **Crust:** `#DAC9B7`
- **Supporting surfaces:** `#E4D7C8`, `#DDCCB8`

### 2.2 Text Ink — Warm Graphite

- **Value:** `#332D29`
- **Role:** Primary body text color.
- **Implementation note:** This is the main light-mode text override used by all three presets.

### 2.3 Structural Accent — Prussian Blue

- **Value:** `#0C6B8A`
- **Role:** Structural highlights, overlay accents, and theme emphasis.
- **Implementation note:** This value is currently wired into the preset accent and overlay variables rather than being limited to one widget type.

---

## 3. Information Color System

The sidebar and heading coloration is implemented through AnuPpuccin's rainbow and heading-color settings, with a watercolor-like palette replacing harsher default primaries.

### Shipped light-mode accent colors

- **Red:** `#C13A4B`
- **Orange / Peach:** `#D6622B`
- **Yellow:** `#B58900`
- **Green:** `#3B8749`
- **Sky:** `#2286B3`
- **Sapphire:** `#355C99`
- **Blue:** `#426BB3`
- **Mauve / Purple:** `#964785`
- **Lavender:** `#6C5CA1`
- **Maroon:** `#993838`

### Rainbow behavior

The shipped presets currently enable:

- rainbow file coloring
- simple rainbow title coloring
- simple rainbow indentation coloring
- rainbow folder background opacity at **`0.80`**

That opacity setting is a key part of the current look: the category colors read as tinted washes rather than solid blocks.

---

## 4. Shared Reading-Surface Language

All three CSS snippets share the same reading-surface treatment, even though each preset keeps its own font stack and text rhythm.

### Common implemented behaviors

- **Article panel as the reading stage** — Markdown views use a soft panel background derived from `var(--code-background)`, with a light border, rounded corners, and a soft shadow.
- **Single-depth code hierarchy** — Code blocks sit visually deeper than article text, while inner `pre code` backgrounds are reset to transparent.
- **Quiet dividers** — Horizontal rules and heading dividers are restored with low-contrast graphite lines.
- **Measured table structure** — Table borders, headers, and row fills are lightly strengthened so they remain readable on warm backgrounds.

This shared layer is implemented in:

- [snippets/antique-vellum-apprentice.css](snippets/antique-vellum-apprentice.css)
- [snippets/antique-vellum-codex.css](snippets/antique-vellum-codex.css)
- [snippets/antique-vellum-feuilleton.css](snippets/antique-vellum-feuilleton.css)

---

## 5. Spatial Pacing & Heading Scale

The current presets share the same heading weights and scale settings through the imported AnuPpuccin preset JSON files.

### Shared heading settings

- **H1:** weight `800`, line-height `1.15`
- **H2:** weight `700`, size `1.8`
- **H3:** weight `600`, size `1.45`
- **H4:** weight `600`
- **H5:** weight `500`
- **H6:** weight `500`, size `1.0`
- **H1 divider:** disabled

These values are currently set in:

- [snippets/antique-vellum-apprentice.json](snippets/antique-vellum-apprentice.json)
- [snippets/antique-vellum-codex.json](snippets/antique-vellum-codex.json)
- [snippets/antique-vellum-feuilleton.json](snippets/antique-vellum-feuilleton.json)

### Cards and spacing

The shipped presets also share these layout values:

- **Card padding:** `1.8em` (`cards-padding`)
- **Card layout padding:** `2.5` (`anp-card-layout-padding`)
- **Card radius:** `10px`
- **Border radius:** `14px`
- **Card border width:** `0px`

So in the current implementation, depth is created mainly through padding, shadow, and radius—not through hard card borders.

---

## Summary

**Antique Vellum & Watercolor Jewel** currently ships as a family of three AnuPpuccin presets with:

- a layered vellum light palette
- warm graphite body text
- Prussian Blue structural accents
- watercolor-style rainbow categorization
- a shared article/code/table reading surface
- preset-specific typography behavior layered on top

For the current typography details, see [typography-rationale-and-spec.md](typography-rationale-and-spec.md).

---

# 📖 设计规范：Antique Vellum & Watercolor Jewel

这是一套以阅读体验为核心的 Obsidian 视觉系统。
本文件描述的是**项目当前已经实现并随仓库一同交付的设计状态**，而不是尚未落地的理想目标。

## 一眼概览

当前实现围绕三个目标展开：

- **让屏幕更像纸，而不是一块发光玻璃。**
- **让色彩承担结构作用，而不是制造噪声。**
- **降低长时间使用时的视觉疲劳。**

在目前仓库中，这些目标具体表现为：

- 一组分层的羊皮纸浅色背景 palette
- 温润石墨正文色
- 克制的普鲁士蓝结构强调
- 基于 AnuPpuccin 的水彩化彩虹分类系统
- 由各方案 CSS snippet 共同实现的阅读界面材质层

---

## 1. 核心视觉方向

这套系统有意避开笔记主题中两种常见极端：

- 高对比、高饱和的“赛博朋克式刺激感”
- 过度冰冷、过度玻璃化的极简风格

当前交付版本追求的是可长期停留的稳定阅读感，而不是短时间的视觉冲击。

### 关键原则

- **物理隐喻**：界面更接近温暖的纸面工作台，而不是一整片发光玻璃。
- **克制层级**：色彩主要承担文件、标题、边界与强调的结构作用。
- **抗疲劳优先**：浅色主题中避免纯黑正文与硬质黑白对冲。

---

## 2. 材质系统

当前实现并不是单一的“羊皮纸纯色底”，而是通过一组浅色表面变量共同构成的**羊皮纸 palette 家族**。

### 2.1 当前 light mode 羊皮纸 palette

目前预设对 AnuPpuccin 浅色变量的覆盖如下：

- **Base:** `#EADFD3`
- **Mantle:** `#E2D4C4`
- **Crust:** `#DAC9B7`
- **辅助表面层:** `#E4D7C8`、`#DDCCB8`

### 2.2 文本墨色：温润石墨

- **色值**：`#332D29`
- **角色**：正文主文字颜色。
- **实现说明**：这是三套预设共用的浅色正文文字覆盖值。

### 2.3 结构强调：普鲁士蓝

- **色值**：`#0C6B8A`
- **角色**：结构高亮、overlay 强调与主题强调色。
- **实现说明**：当前实现中，这个值被接入多组预设 accent / overlay 变量，而不只局限在单一控件。

---

## 3. 信息色彩系统

侧边栏与标题的分类色，当前通过 AnuPpuccin 的 rainbow 与 heading-color 相关设置实现，并以更沉稳的“水彩宝石色”替换默认更刺激的原色倾向。

### 当前实现中的浅色强调色

- **红**：`#C13A4B`
- **橙 / Peach**：`#D6622B`
- **黄**：`#B58900`
- **绿**：`#3B8749`
- **Sky**：`#2286B3`
- **Sapphire**：`#355C99`
- **Blue**：`#426BB3`
- **Mauve / 紫**：`#964785`
- **Lavender**：`#6C5CA1`
- **Maroon**：`#993838`

### 当前 rainbow 行为

目前预设启用了：

- rainbow 文件着色
- simple rainbow 标题着色
- simple rainbow 缩进着色
- rainbow folder 背景透明度 **`0.80`**

这个 `0.80` 透明度正是当前视觉气质的重要来源：分类色看起来更像纸面上的染色层，而不是实心色块。

---

## 4. 共享的阅读界面语言

虽然三套方案的字体与排版节奏不同，但三份 CSS snippet 共享同一套阅读界面处理。

### 当前已经实现的共同规则

- **文章面板作为阅读舞台**：Markdown 视图使用从 `var(--code-background)` 派生的柔和 panel，并带有轻边框、圆角与阴影。
- **单层级代码深度**：代码块比正文更深一层，但内部 `pre code` 背景被重置为透明。
- **安静的分割线**：`hr` 与标题分割线都以低对比的石墨线条恢复可见性。
- **克制的表格结构**：表格边框、表头和行底色被轻度增强，以保证在暖色背景上依然清晰。

这一共享层由以下文件实现：

- [snippets/antique-vellum-apprentice.css](snippets/antique-vellum-apprentice.css)
- [snippets/antique-vellum-codex.css](snippets/antique-vellum-codex.css)
- [snippets/antique-vellum-feuilleton.css](snippets/antique-vellum-feuilleton.css)

---

## 5. 空间律动与标题音阶

当前三套预设通过导入的 AnuPpuccin preset JSON，共享同一组标题字重与字号参数。

### 当前共享的标题设定

- **H1：** 字重 `800`，行高 `1.15`
- **H2：** 字重 `700`，字号 `1.8`
- **H3：** 字重 `600`，字号 `1.45`
- **H4：** 字重 `600`
- **H5：** 字重 `500`
- **H6：** 字重 `500`，字号 `1.0`
- **H1 分割线：** 关闭

这些值目前写在：

- [snippets/antique-vellum-apprentice.json](snippets/antique-vellum-apprentice.json)
- [snippets/antique-vellum-codex.json](snippets/antique-vellum-codex.json)
- [snippets/antique-vellum-feuilleton.json](snippets/antique-vellum-feuilleton.json)

### 卡片与留白

当前三套预设还共享以下布局参数：

- **卡片内边距：** `1.8em`（`cards-padding`）
- **卡片布局内边距：** `2.5`（`anp-card-layout-padding`）
- **卡片圆角：** `10px`
- **通用圆角：** `14px`
- **卡片边框宽度：** `0px`

因此，在当前实现里，层级感主要由留白、阴影和圆角建立，而不是由硬边框建立。

---

## 总结

**Antique Vellum & Watercolor Jewel** 当前交付的是三套基于 AnuPpuccin 的主题预设，它们共同具备：

- 分层的羊皮纸浅色 palette
- 温润石墨正文色
- 普鲁士蓝结构强调
- 水彩化的彩虹分类系统
- 共享的文章 / 代码 / 表格阅读界面材质层
- 在其之上叠加的各方案专属排版行为

当前字体实现细节，请继续参见 [typography-rationale-and-spec.md](typography-rationale-and-spec.md)。
