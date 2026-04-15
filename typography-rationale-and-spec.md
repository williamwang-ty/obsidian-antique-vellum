# Typography Design Spec / 字体排版设计规范

This document extends **Antique Vellum & Watercolor Jewel** at the typography level.
It describes the three **currently implemented** typography presets in this repository, and how their behavior is actually delivered through the CSS snippets.

本文件是 **Antique Vellum & Watercolor Jewel** 在排版层面的扩展说明。
它描述的是仓库中三套**当前已实现**的排版方案，以及这些行为如何通过 CSS snippet 实际落地。

---

## 0. Core Typography Model

## 0. 核心排版模型

The current implementation is not optimized only for information density.
It is designed to support three things at the same time:

- **stable reading mood**
- **continuous reading rhythm**
- **long-session visual comfort**

In practice, that goal is delivered through three layers:

1. **Shared reading-surface layer** — article panel, code-block depth, dividers, and table boundaries
2. **Preset-level font stack** — each preset's body-text and code-font selection
3. **Preset-level microtypography** — line height, letter spacing, inline title behavior, and local title handling

当前实现的排版目标，并不只是追求信息密度。
它同时服务于三件事：

- **稳定的阅读情绪**
- **连续的阅读节奏**
- **长时间使用下的视觉舒适度**

在实际落地中，这个目标通过三层共同完成：

1. **共享阅读界面层** —— 文章 panel、代码块深度、分割线、表格边界
2. **预设级字体栈** —— 每个方案各自的正文与代码字体选择
3. **方案级微排版** —— 行高、字距、inline title 行为与局部标题处理

---

## 1. The Three Shipped Typography Presets

## 1. 三套当前交付的排版方案

### 1.1 Apprentice

### 1.1 Apprentice 修艺之士

**Best for**
Users working under sustained learning pressure who want a note space that feels gentle and supportive without becoming childish. It is well suited to long-term study notes, skill-building, and knowledge construction.

**适合场景**
适合处于高压学习状态、希望页面能以亲切柔和的质感承接思绪的人。它适合作为长期学习笔记、技能打磨与知识构建空间，是陪伴使用者日复一日修炼技艺的学徒案台。

#### Current font stack

#### 当前字体栈

- **Body / editor font:** `"QiushuiCJK", "KaitiCJK", "Crimson Pro", "Crimson Text", "Iowan Old Style", "Constantia", "Palatino", "Palatino Linotype", serif`
- **Code font:** `"OperatorMonoBook", "Menlo", "Consolas", "KaitiCJK", "QiushuiCJK", monospace`
- **Inline title font:** `"HiraginoSansGBTitle", "Crimson Pro", "Crimson Text", "Iowan Old Style", "Constantia", "Palatino", "Palatino Linotype", serif`

- **正文 / 编辑器字体：** `"QiushuiCJK", "KaitiCJK", "Crimson Pro", "Crimson Text", "Iowan Old Style", "Constantia", "Palatino", "Palatino Linotype", serif`
- **代码字体：** `"OperatorMonoBook", "Menlo", "Consolas", "KaitiCJK", "QiushuiCJK", monospace`
- **Inline Title 字体：** `"HiraginoSansGBTitle", "Crimson Pro", "Crimson Text", "Iowan Old Style", "Constantia", "Palatino", "Palatino Linotype", serif`

#### Current implemented behavior

#### 当前实现行为

- Uses `@font-face` to define three CJK proxy fonts and one local code-font mapping: `QiushuiCJK`, `KaitiCJK`, `HiraginoSansGBTitle`, and `OperatorMonoBook`
- Body line height: `1.65`
- Body letter spacing: `0.02em`
- No extra body `word-spacing`
- Body / list / table text scaled to `1.1x`
- Inline title scaled to `1.30 × H1`
- Code blocks are designed as manuscript inserts rather than dense IDE slabs:
  - humanist code stack led by `OperatorMonoBook`, with `Menlo` and `Consolas` as pragmatic fallbacks
  - CJK comments fall back to `KaitiCJK` / `QiushuiCJK`
  - `line-height: 1.5`
  - `letter-spacing: 0`
  - `word-spacing: 0`
  - `font-size: 0.94 × base`
  - block padding: `1.05em 1.35em`
- Inline code is reduced to `0.9em` with subtle horizontal padding so it behaves like an annotation inside prose
- Code comments use true italic styling where the selected code font provides it

- 通过 `@font-face` 定义了三个 CJK 代理字体与一个本地代码字体映射：`QiushuiCJK`、`KaitiCJK`、`HiraginoSansGBTitle`、`OperatorMonoBook`
- 正文行高：`1.65`
- 正文字距：`0.02em`
- 不再额外设置正文 `word-spacing`
- 正文 / 列表 / 表格文字放大到 `1.1x`
- Inline Title 放大为 `1.30 × H1`
- 代码块不再被当作高密度 IDE 面板，而是被设计为嵌在纸面里的“手稿插页”：
  - 以 `OperatorMonoBook` 为首选的人文等宽栈，`Menlo` 与 `Consolas` 作为务实回退
  - 中文注释回退到 `KaitiCJK` / `QiushuiCJK`
  - `line-height: 1.5`
  - `letter-spacing: 0`
  - `word-spacing: 0`
  - `font-size: 0.94 × base`
  - 区块内边距：`1.05em 1.35em`
- 行内代码缩小到 `0.9em`，并加入极轻的水平内边距，使其在正文中更像批注而不是 UI 标签
- 若所选代码字体提供真正的斜体，代码注释会使用 true italic 形态

#### Note

#### 说明

Apprentice is tuned primarily for CJK reading. It keeps body `letter-spacing: 0.02em` for Chinese breathing room and removes extra `word-spacing` so English does not open up too much. If your notes are mainly English, reduce or remove that body `letter-spacing`.

Apprentice 目前以中文阅读为优先。正文保留 `letter-spacing: 0.02em` 以维持中文呼吸感，并移除了额外 `word-spacing` 以避免英文过松。若内容以英文为主，可适当减小或移除该 `letter-spacing`。

#### Code-area design

#### 代码区设计

Apprentice treats code as a manuscript insert rather than a dense IDE slab. Latin code prefers `OperatorMonoBook` with `Menlo` / `Consolas` fallbacks, while Chinese comments route to `KaitiCJK` / `QiushuiCJK`. Inline code is slightly reduced so it sits inside prose more naturally.

Apprentice 将代码区处理为“手稿插页”，而不是高密度 IDE 面板。拉丁代码优先使用 `OperatorMonoBook`，并回退到 `Menlo` / `Consolas`；中文注释则路由到 `KaitiCJK` / `QiushuiCJK`。行内代码会略微缩小，以便更自然地嵌入正文。

#### What defines this preset in practice

#### 这个方案在当前实现中的核心特征

In the current repository, Apprentice is defined less by an abstract “manuscript feeling” and more by five concrete implementation choices tied directly to the learning scenario:

- Qiushui Shotai CJK routing keeps the body text gentle（ex. LXGW WenKai） while preserving a clean and sharp textbook quality (ex. Yu Kyokasho), avoiding a childish tone(LXGW WenKai)
- a Crimson-centered Latin stack keeps English warm, clear, and slightly restrained, so mixed-language text feels intimate without becoming overly sweet or mechanically bookish
- `Hiragino Sans GB` gives titles enough authority to hold the page without the heavier pressure of Song / Ming styles
- larger body scaling and looser spacing create a calmer, more breathable rhythm for sustained study
- code is treated as a manuscript insert rather than a detached IDE layer, using a humanist monospace voice, softened block spacing, and true italic comments where available

在当前仓库中，Apprentice 与其说是靠抽象的“手稿感”成立，不如说是由五项直接服务学习场景的实现决定：

- 通过秋水书体作为主 CJK 路由，让正文既亲切柔和（如霞鹜文楷），又保持干净锐利（如日文教科书体）、不过分幼态（霞鹜文楷）
- 通过以 `Crimson Pro / Crimson Text` 为核心的西文字体栈，让英文保留手稿温度，同时维持清秀、克制、不过度甜美也不过度印刷化的气质
- 通过 `Hiragino Sans GB` 为标题建立足够的压阵力，避免今楷偏软、宋体偏重的问题
- 通过更大的正文倍率与更松的字距制造更安静、更有呼吸感的学习节奏
- 通过把代码区处理成“手稿插页”而不是脱离页面的 IDE 面板，并使用人文等宽语调、柔化后的区块留白与可用时的真斜体注释，让技术内容也纳入同一套阅读气候

Implementation files:
- [snippets/antique-vellum-apprentice.css](snippets/antique-vellum-apprentice.css)
- [snippets/antique-vellum-apprentice.json](snippets/antique-vellum-apprentice.json)

实现文件：
- [snippets/antique-vellum-apprentice.css](snippets/antique-vellum-apprentice.css)
- [snippets/antique-vellum-apprentice.json](snippets/antique-vellum-apprentice.json)

---

### 1.2 Codex

### 1.2 Codex 学术雕版

**Best for**  
Long-form reading, literature management, research notes, and dense knowledge archives. It is the most restrained and stable of the three presets.

**适合场景**  
适合长篇阅读、文献管理、研究笔记与高密度知识归档。它是三套方案中最收敛、最稳定的一套。

#### Current font stack

#### 当前字体栈

- **Body / editor font:** `"Charter", "Bitstream Charter", "Palatino", "Palatino Linotype", "Noto Serif SC", "Source Han Serif SC", serif`
- **Code font:** `"IBM Plex Mono", var(--font-monospace), monospace`

- **正文 / 编辑器字体：** `"Charter", "Bitstream Charter", "Palatino", "Palatino Linotype", "Noto Serif SC", "Source Han Serif SC", serif`
- **代码字体：** `"IBM Plex Mono", var(--font-monospace), monospace`

#### Current implemented behavior

#### 当前实现行为

- Body line height: `1.6`
- Body letter spacing: `0.01em`
- No additional body text scaling
- Inline title scaled to `1.3 × H1`
- Code blocks use `IBM Plex Mono` without the extra compressed code metrics seen in Apprentice

- 正文行高：`1.6`
- 正文字距：`0.01em`
- 没有额外的正文字号放大
- Inline Title 放大为 `1.3 × H1`
- 代码块使用 `IBM Plex Mono`，但没有像 Apprentice 那样额外压缩 code metrics

#### What defines this preset in practice

#### 这个方案在当前实现中的核心特征

Codex is currently defined by:

- a steadier line height and tighter spacing for a literature-page rhythm
- code blocks that still sit one level deeper than article text, but without extra code-size or code-line-height compression
- the same shared reading-surface layer used by the other presets

Codex 当前主要由以下特征定义：

- 更稳的行高与更收的字距，形成接近文献页的节奏
- 代码块依旧比正文更深一层，但不会额外压缩代码字号或代码行高
- 与其他方案共享同一套阅读界面层

Implementation files:
- [snippets/antique-vellum-codex.css](snippets/antique-vellum-codex.css)
- [snippets/antique-vellum-codex.json](snippets/antique-vellum-codex.json)

实现文件：
- [snippets/antique-vellum-codex.css](snippets/antique-vellum-codex.css)
- [snippets/antique-vellum-codex.json](snippets/antique-vellum-codex.json)

---

### 1.3 Feuilleton

### 1.3 Feuilleton 贵智专栏

**Best for**  
Opinionated notes, essay-like writing, and content that benefits from stronger title presence and column-like editorial tone.

**适合场景**  
适合评论性笔记、随笔式写作，以及更依赖标题气场与专栏感的内容。

#### Current font stack

#### 当前字体栈

- **Body / editor font:** `"EB Garamond", "Adobe Garamond Pro", "Garamond Premier Pro", "Baskerville", "Iowan Old Style", "Palatino", "Palatino Linotype", "HYCuFangSongJCJK", "Noto Serif SC", "Songti SC", "Source Han Serif SC", serif`
- **Code font:** `"Consolas", "Input Mono", "Berkeley Mono", "Menlo", "Kaiti SC", "STKaiti", "Kaiti TC", "HYCuFangSongJCJK", monospace`
- **Inline title font:** `"Didot", "Bodoni MT", "HYCuFangSongJCJK", ui-serif, serif`

- **正文 / 编辑器字体：** `"EB Garamond", "Adobe Garamond Pro", "Garamond Premier Pro", "Baskerville", "Iowan Old Style", "Palatino", "Palatino Linotype", "HYCuFangSongJCJK", "Noto Serif SC", "Songti SC", "Source Han Serif SC", serif`
- **代码字体：** `"Consolas", "Input Mono", "Berkeley Mono", "Menlo", "Kaiti SC", "STKaiti", "Kaiti TC", "HYCuFangSongJCJK", monospace`
- **Inline Title 字体：** `"Didot", "Bodoni MT", "HYCuFangSongJCJK", ui-serif, serif`

#### Current implemented behavior

#### 当前实现行为

- Body line height: `1.75`
- Body letter spacing: `0.012em`
- Body text uses `font-weight: 400`
- Body / list / table text scaled to `1.18x`
- Feuilleton now uses a dedicated `@font-face` + `unicode-range` proxy so Latin text stays on `EB Garamond` while CJK text can route to `HYCuFangSongJ`
- Inline title scaled to `1.3 × H1`
- Inline title forces display serif styling with:
  - `text-transform: uppercase`
  - `font-weight: 400`
  - `line-height: 1.25`
- Code blocks now prioritize `Consolas` for a cooler, more controlled editorial voice, with `Input Mono` / `Berkeley Mono` behind it, while routing CJK inside code to `Kaiti SC` / `STKaiti` to avoid modern black-sans fallbacks
- The current CSS **does not** enable `-webkit-text-stroke: 0.25px ...` for body text; instead, headings, bold text, code, and related elements are explicitly reset to `0px` stroke

- 正文行高：`1.75`
- 正文字距：`0.012em`
- 正文使用 `font-weight: 400`
- 正文 / 列表 / 表格文字放大到 `1.18x`
- Feuilleton 现在通过专门的 `@font-face` + `unicode-range` 代理层，让西文继续使用 `EB Garamond`，同时让 CJK 文本可路由到 `HYCuFangSongJ`
- Inline Title 放大为 `1.3 × H1`
- Inline Title 强制使用展示级 serif 样式，并启用：
  - `text-transform: uppercase`
  - `font-weight: 400`
  - `line-height: 1.25`
- 代码块现在优先使用更冷静、更稳的 `Consolas`，并以 `Input Mono` / `Berkeley Mono` 作为后续回退，同时将代码内 CJK 路由到 `Kaiti SC` / `STKaiti`，避免出现现代黑体 fallback
- 当前 CSS **没有**对正文启用 `-webkit-text-stroke: 0.25px ...`；相反，标题、粗体、代码及相关元素都被显式重置为 `0px` 描边

#### What defines this preset in practice

#### 这个方案在当前实现中的核心特征

Feuilleton currently gets its editorial / magazine-like tone mainly from:

- larger body scaling and looser line height
- Didot / Bodoni-style inline titles
- uppercase and regular-weight inline-title handling

It is **not** currently defined by body-text stroke.

Feuilleton 当前的专栏 / 杂志感，主要来自：

- 更大的正文倍率与更松的行高
- Didot / Bodoni 风格的 inline title
- inline title 的 uppercase 与常规字重处理

它当前**不是**靠正文描边建立气质。

Implementation files:
- [snippets/antique-vellum-feuilleton.css](snippets/antique-vellum-feuilleton.css)
- [snippets/antique-vellum-feuilleton.json](snippets/antique-vellum-feuilleton.json)

实现文件：
- [snippets/antique-vellum-feuilleton.css](snippets/antique-vellum-feuilleton.css)
- [snippets/antique-vellum-feuilleton.json](snippets/antique-vellum-feuilleton.json)

---

## 2. Relationship to the Overall Design System

## 2. 与整体设计系统的关系

These three presets are not independent themes.
They run on top of the same underlying visual system.

这三套方案并不是彼此独立的主题。
它们运行在同一套底层视觉系统之上。

### Shared assumptions in the current implementation

### 当前实现中的共享前提

1. **Unified body-text color**  
   All three presets use `#332D29` as the main light-mode body-text override.

2. **Shared reading-surface layer**  
   All three presets share the same treatment for:
   - soft article panel
   - deeper code-block surface
   - quiet dividers
   - lightly strengthened table structure

3. **Shared structural accent color**  
   Prussian Blue `#0C6B8A` is wired into accent / overlay-related variables and functions as the current structural accent color.

4. **Shared heading settings**  
   All three presets share the same AnuPpuccin heading configuration:
   - H1 `800 / 1.15`
   - H2 `700 / 1.8`
   - H3 `600 / 1.45`
   - H4 `600`
   - H5 `500`
   - H6 `500 / 1.0`

1. **正文主色统一**  
   三套方案都使用 `#332D29` 作为浅色模式的主正文覆盖色。

2. **共享阅读界面层**  
   三套方案共享同一套处理方式，包括：
   - 柔和的 article panel
   - 更深一层的 code-block 表面
   - 安静的分割线
   - 轻度强化的表格结构

3. **共享结构强调色**  
   普鲁士蓝 `#0C6B8A` 被接入 accent / overlay 相关变量，作为当前实现中的结构强调色。

4. **共享标题设定**  
   三套方案共用同一组 AnuPpuccin 标题配置：
   - H1 `800 / 1.15`
   - H2 `700 / 1.8`
   - H3 `600 / 1.45`
   - H4 `600`
   - H5 `500`
   - H6 `500 / 1.0`

For the broader color and surface system, see [design-system-rationale.md](design-system-rationale.md).

更完整的色彩与阅读界面系统，请参见 [design-system-rationale.md](design-system-rationale.md)。

---

## 3. Why a Font-Isolation Layer Exists

## 3. 为什么需要字体隔离层

In this project, the font-isolation layer is **not** a universal mechanism used by all three presets.
At the moment, it is used by **Apprentice** and **Feuilleton**, while **Codex** still uses a normal stack.

The reason is simple: many CJK fonts ship with their own Latin glyphs.
When the browser resolves `font-family`, it matches character by character. If the current font can render a character, it will stop there instead of continuing down the stack.

That creates a common problem: even if Latin text is supposed to use a Latin serif, a CJK font may silently take over if the earlier Latin font is unavailable.

在当前项目里，字体隔离层**不是**三套方案都统一启用的机制。
目前使用它的是 **Apprentice** 和 **Feuilleton**，而 **Codex** 仍然使用普通字体栈。

原因很直接：很多 CJK 字体本身自带拉丁字形。
浏览器解析 `font-family` 时，会逐字符匹配；只要当前字体能渲染该字符，就不会继续往后找。

这会导致一个常见问题：即使本来希望西文由西文字体负责，只要前面的西文字体不可用，CJK 字体就可能静默接管西文字符。

---

## 4. How It Is Implemented in This Repository

## 4. 它在当前仓库中的实现方式

In the current repository, the implemented solution lives in [snippets/antique-vellum-apprentice.css](snippets/antique-vellum-apprentice.css) and [snippets/antique-vellum-feuilleton.css](snippets/antique-vellum-feuilleton.css).

They use `@font-face` + `unicode-range` to define CJK-only proxy fonts:

- `QiushuiCJK`
- `KaitiCJK`
- `HiraginoSansGBTitle`
- `HYCuFangSongJCJK`

Example:

在当前仓库里，已经落地的解决方案位于 [snippets/antique-vellum-apprentice.css](snippets/antique-vellum-apprentice.css) 与 [snippets/antique-vellum-feuilleton.css](snippets/antique-vellum-feuilleton.css)。

它们通过 `@font-face` + `unicode-range` 定义仅负责 CJK 的代理字体：

- `QiushuiCJK`
- `KaitiCJK`
- `HiraginoSansGBTitle`
- `HYCuFangSongJCJK`

示例：

```css
@font-face {
    font-family: "QiushuiCJK";
    src: local("QiushuiShotai");
    unicode-range: U+4E00-9FFF, U+3400-4DBF, U+20000-2A6DF, U+F900-FAFF, U+3000-303F, U+FF00-FFEF, U+2E80-2EFF, U+FE30-FE4F;
}
```

This means:

- CJK characters are routed to those proxy fonts
- Latin characters continue down to the Crimson-centered serif stack: `Crimson Pro` / `Crimson Text` / `Iowan Old Style` / `Constantia` / `Palatino`
- the Chinese portion of inline titles can be routed separately to `HiraginoSansGBTitle`

That also means something important about the current implementation:
**Apprentice and Feuilleton explicitly ship this `@font-face` + `unicode-range` layer.**
Codex still relies on a normal font stack.

In Feuilleton, this is used to keep Latin text on `EB Garamond` while routing CJK body text to `HYCuFangSongJ`.

这意味着：

- CJK 字符会被路由到这些代理字体
- Latin 字符会继续落到以 `Crimson Pro` / `Crimson Text` / `Iowan Old Style` / `Constantia` / `Palatino` 为核心的 serif 栈
- inline title 的中文部分还能单独落到 `HiraginoSansGBTitle`

这也说明当前实现中的一个关键事实：
**Apprentice 与 Feuilleton 都明确交付了这层 `@font-face` + `unicode-range` 机制。**
Codex 目前仍然依赖普通 font stack。

在 Feuilleton 中，这层机制用来让西文继续使用 `EB Garamond`，同时把中文正文路由到 `HYCuFangSongJ`。

---

## 5. Current Coverage

## 5. 当前实现覆盖范围

Based on the repository as it exists now, explicit font-isolation and title-font routing coverage is:

| Preset | Current proxy-font coverage |
|---|---|
| Apprentice | `QiushuiCJK`, `KaitiCJK`, `HiraginoSansGBTitle` |
| Codex | No dedicated `@font-face` proxy layer |
| Feuilleton | `HYCuFangSongJCJK` |

按当前仓库现状，明确实现了字体隔离与标题字体分流的覆盖范围如下：

| 方案 | 当前代理字体覆盖 |
|---|---|
| Apprentice | `QiushuiCJK`, `KaitiCJK`, `HiraginoSansGBTitle` |
| Codex | 没有独立的 `@font-face` 代理层 |
| Feuilleton | `HYCuFangSongJCJK` |

---

## 6. Deployment Model

## 6. 启用方式

In the current repository, each typography preset is enabled as a **preset + matching snippet** pair:

1. Import the matching `.json` preset
2. Enable the matching `.css` snippet
3. If using Apprentice, make sure `QiushuiShotai` is installed as a system font

In the current implementation:

- the preset mainly controls palette, heading weights, layout values, and rainbow behavior
- the snippet mainly controls the reading-surface layer, font overrides, and preset-specific typography behavior

For the full installation workflow, see [README.md](README.md).

在当前仓库中，每套排版方案都通过 **preset + 对应 snippet** 的组合启用：

1. 导入对应的 `.json` preset
2. 启用对应的 `.css` snippet
3. 如果使用 Apprentice，确保 `QiushuiShotai` 已作为系统字体安装

在当前实现里：

- preset 主要控制 palette、标题字重、布局参数与 rainbow 行为
- snippet 主要控制阅读界面层、字体覆盖与方案级排版行为

完整安装流程请参见 [README.md](README.md)。
