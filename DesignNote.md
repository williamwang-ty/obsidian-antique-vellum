# 📖 Design Specification: Antique Vellum & Watercolor Jewel

**System Positioning:** An immersive visual system for personal knowledge management (PKM), designed for intensive text workers, architects, and researchers.

**Core Philosophy:** Weaving the **"patina of physical paper"** with the **"high-dimensional information architecture"** of the digital realm, pursuing low cognitive load and comfortable eye protection.

## 1. Core Visual Philosophy

This design consciously steps away from the high-contrast, over-saturated "cyberpunk" and sterile minimalist trends prevalent in modern digital products. Knowledge accumulation benefits from physical warmth.

- **Physical Metaphor:** The interface should not feel like a sheet of glowing glass, but rather a well-worn parchment folio.
- **Restrained Elegance:** Color is not utilized for visual spectacle, but acts as an invisible navigational anchor for information hierarchy.
- **Anti-Fatigue Priority:** Avoiding the halation effect on the retina caused by absolute black (`#000000`) and pure white/black backgrounds.

---

## 2. Color Space & Material System

Grounded in the LCH color space, the system is deconstructed into three primary material layers, ensuring they remain visually distinct yet harmoniously blended.

### 2.1 Surface & Background: Antique Vellum

- **Set Value:** `#C8B195` (Light Mode)
- **Design Rationale:** Abandoning generic light grays or stark whites, this tone simulates the roasted, latte-like patina caused by the oxidation of lignin in aging paper. This base color filters out the harsh glare of the screen, providing a quiet, "study-room" ambiance that is easy on the eyes over long sessions.

### 2.2 Text Ink: Warm Graphite

- **Set Value:** `#332D29` (Deep Graphite / Charcoal Black)
- **Design Rationale:** Stark black on a darkened paper background creates visual dissonance. The text is calibrated to a deep gray infused with subtle warm undertones, mimicking the trace of an aged charcoal pencil — ink slightly absorbed into the paper fibers. The contrast clears the legibility threshold while remaining soft and free of glare.

### 2.3 Accent & Overlay: Prussian Blue

- **Set Value:** `#0C6B8A` (Prussian Blue / Fountain Pen Ink)
- **Design Rationale:** UI interactive elements (highlight borders, accent lines) require a cool-warm juxtaposition against the paper. All "digitally native" fluorescent cyans are replaced with a grounded Prussian Blue. It serves as the rational "skeleton" of the interface — restrained and never stealing the spotlight.

---

## 3. Information Color Architecture: Watercolor Jewel Tones

Within the "Rainbow System" of sidebar folders and headings, high-purity primary colors are replaced with organic "Jewel Tones" found in nature.

- **Color Mapping:**

    - **Red:** `#C13A4B` (Burgundy) — For critical or core emphasis.
    - **Orange:** `#D6622B` (Vintage Terracotta) — For secondary warnings or progression.
    - **Yellow:** `#B58900` (Naples Amber) — Replacing harsh lemon yellow to guarantee legibility on the paper background.
    - **Green:** `#3B8749` (Vintage Emerald) — For success states or stable categorizations.
    - **Blue/Cyan:** `#355C99` (Lapis Lazuli) / `#2286B3` (Maldives Blue) — For primary classifications within the knowledge base.
    - **Purple:** `#964785` (Byzantine Purple) — For unique or archival entries.

- **Watercolor Opacity:** Rainbow folder background opacity set to **`0.85`**.

    - **Design Rationale:** Lowering the opacity gives the jewel tones a semi-transparent, "watercolor wash" texture, allowing the labels to undergo optical mixing with the underlying parchment. The colors no longer feel like plastic stickers floating on the surface — they become pigments bled into the paper.

---

## 4. Spatial Pacing & Typographic Scale

Following the negative space philosophy of the Apple Human Interface Guidelines and the traditional Modular Scale, a clear visual waterfall is established.

### 4.1 Font and Weight Distribution

Using the humanist serif font `New York`, paired with a weight-degradation system to address the "top-heavy" typographic issue.

- **H1 (Weight 800 / Line-height 1.15):** The anchoring centerpiece of the page. Tightened line height prevents multiline titles from falling apart. The divider line is removed — relying on typographic weight alone to hold the space.
- **H2 (Weight 700 / Size 1.8) → H3 (Weight 600 / Size 1.45):** A smooth visual step-down.
- **H4 (600) → H5 (500) → H6 (500 / Size 1.0):** Terminal headings take on a texture akin to "Small Caps" — reduced size but maintained weight, preserving hierarchical clarity even in deeply nested notes.

### 4.2 Card Containers & Breathing Space

- **Card Padding:** `1.8em` (cards-padding) and `2.5` (anp-card-layout-padding).
- **Border Radius:** `10px` and `14px`.
- **Borderless Shadow:** `cards-border-width: 0px`.

    - **Design Rationale:** Hard physical borders are removed entirely. Generous negative space and subtle card shadows handle depth separation instead. Combined with rounded "Squircle"-level corner transitions, each information block sits like a card resting on the parchment — blending vintage texture with modern UI layout.

---

**Design Summary:**

This design system is not a simple accumulation of colors, but a deliberate calibration of psychology and optics. The Prussian Blue framework disciplines the rationality of knowledge, while warm graphite and watercolor-washed parchment soothe the writer's sensibility. It is a typographic system built around the act of reading.

---

# 📖 设计规范：Antique Vellum & Watercolor Jewel

**系统定位**：为高强度文字工作者、架构师与研究员打造的沉浸式个人知识库视觉系统。

**核心理念**：将物理世界的 **"岁月纸媒质感"** 与数字世界的 **"高维信息架构"** 结合，追求低认知负荷与舒适的视力保护。

## 1. 核心视觉哲学

本设计有意回避现代数字产品中常见的高对比度、高饱和度的赛博朋克或极简冷淡风。知识的沉淀需要物理温度。

- **物理隐喻**：界面不应是发光的玻璃，而应是存放了半个世纪的羊皮卷宗。
- **克制的高级**：色彩不用于炫技，而是作为信息层级的隐形导航。
- **抗疲劳优先**：避免纯黑（`#000000`）与纯白/纯黑背景带来的视网膜光晕效应（Halation）。

---

## 2. 色彩空间与材质系统

基于 LCH 色彩空间，将系统拆分为三大材质层，确保它们在视觉上既有区分度，又能互相交融。

### 2.1 纸张底色：岁月羊皮纸

- **设定值**：`#C8B195`（Light Mode）
- **设计考量**：摒弃普通的浅灰或死白，模拟纸张内部木质素（Lignin）随岁月氧化后的重度烤色/拿铁色。这种厚重的底色过滤了屏幕的白光刺射，提供一种"书斋"般的沉静感，对长时间阅读友好。

### 2.2 文本墨水：温润炭笔

- **设定值**：`#332D29`（深石墨灰 / 炭笔黑）
- **设计考量**：在深色纸张上使用纯黑会产生强烈的视觉割裂感。文本色调配为带有微弱暖色调的深灰，模拟存放多年的炭笔痕迹——墨水仿佛微微晕染进了纸张纤维中，对比度恰好跨过易读性阈值，柔和且不刺眼。

### 2.3 骨架与边框：普鲁士蓝

- **设定值**：`#0C6B8A`（普鲁士蓝 / 钢笔墨水蓝）
- **设计考量**：UI 的交互元素（高亮边框、强调线）需要与纸张的暖色形成冷暖互补。去除所有"数字原生"的荧光青色，采用沉稳的普鲁士蓝。它在界面中充当理性的"骨架"，克制而不抢戏。

---

## 3. 信息色彩架构：水彩宝石色系

在侧边栏文件夹与标题的"彩虹系统"中，用自然界的 **"宝石色系（Jewel Tones）"** 替换高纯度的原色。

- **色彩映射表**：

    - **红**：`#C13A4B`（勃艮第酒红）— 用于高危或核心强调
    - **橙**：`#D6622B`（复古赤陶）— 用于次级警告或进度
    - **黄**：`#B58900`（那不勒斯琥珀）— 替代刺眼的柠檬黄，保证在纸张上的辨识度
    - **绿**：`#3B8749`（复古祖母绿）— 用于成功或平稳的分类
    - **蓝/青**：`#355C99`（青金石）/ `#2286B3`（马尔代夫海蓝）— 用于知识库的主体分类
    - **紫**：`#964785`（拜占庭紫）— 用于特殊或归档条目

- **水彩晕染设定**：彩虹背景透明度设定为 **`0.85`**。

    - **设计考量**：降低透明度让宝石色呈现出"水彩晕染"的半透质感，使标签色彩与底部的羊皮纸背景产生光学混合（Optical Mixing）。颜色不再是浮在表面的塑料贴纸，而是渗入纸张的颜料。

---

## 4. 空间律动与排版音阶

遵循 Apple Human Interface Guidelines 的留白哲学与传统的模数比例（Modular Scale），构建清晰的视觉层级。

### 4.1 字体与字重分配

使用人文衬线体 `New York`，配合字重降级系统，解决"头重脚轻"的排版问题。

- **H1（800 / 行高 1.15）**：页面的视觉锚点。行高收紧防止多行散架，取消下划线分割，依赖自身字重压住全场。
- **H2（700 / 字号 1.8）→ H3（600 / 字号 1.45）**：平滑的视觉降级。
- **H4（600）→ H5（500）→ H6（500 / 字号 1.0）**：末端标题引入类似"小型大写字母"的质感，字号小但保持一定的字重，确保在深层嵌套的笔记中依然具备层级清晰度。

### 4.2 卡片容器与呼吸感

- **卡片内边距**：`1.8em`（cards-padding）与 `2.5`（anp-card-layout-padding）。
- **圆角曲率**：`10px` 和 `14px`。
- **无边框阴影**：`cards-border-width: 0px`。

    - **设计考量**：移除生硬的物理边框，转而利用大留白与微妙的卡片阴影来区分层级。配合"超椭圆（Squircle）"级别的圆角过渡，各个信息块仿佛是悬浮在羊皮纸上的卡片，兼顾了物理复古感与现代 UI 布局。

---

**设计总结**：

这套设计系统不是简单的颜色堆砌，而是一场心理学与光学的微调。普鲁士蓝的框架约束知识的理性，温润的石墨与水彩晕染的羊皮纸抚慰书写者的感性。它是一个围绕"阅读"这件事来构建的排版系统。