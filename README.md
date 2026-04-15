# Antique Vellum

[中文](#中文) · [English](#english)

---

## 中文

> 一套护眼的 Obsidian 主题预设——暖调羊皮纸层次、水彩化强调色，以及适合长时阅读的界面体验。
>
> 本项目优先追求尽可能极致的视觉效果，而不是字体安装的便利性。部分字体可能需要你自行搜索、下载并手动安装。

### 包含内容

#### 预设文件

| 文件 | 说明 |
|---|---|
| [snippets/antique-vellum-apprentice.json](snippets/antique-vellum-apprentice.json) | 方案一：Apprentice |
| [snippets/antique-vellum-apprentice.css](snippets/antique-vellum-apprentice.css) | Option 1 核心 snippet：语种隔离、字体覆盖与排版微调 |
| [snippets/antique-vellum-codex.json](snippets/antique-vellum-codex.json) | 方案二：Codex |
| [snippets/antique-vellum-codex.css](snippets/antique-vellum-codex.css) | Option 2 核心 snippet：字体覆盖、排版微调与阅读界面层 |
| [snippets/antique-vellum-feuilleton.json](snippets/antique-vellum-feuilleton.json) | 方案三：Feuilleton |
| [snippets/antique-vellum-feuilleton.css](snippets/antique-vellum-feuilleton.css) | Option 3 核心 snippet：字体覆盖、排版微调与阅读界面层 |

#### 文档

| 文件 | 说明 |
|---|---|
| [design-system-rationale.md](design-system-rationale.md) | 设计思路与当前实现说明 |
| [typography-rationale-and-spec.md](typography-rationale-and-spec.md) | 字体排版系统与实现细节 |

#### 演示

| 文件 | 说明 |
|---|---|
| [demo/typography-demo-zh.html](demo/typography-demo-zh.html) | 适合中英混排 / 中文内容的排版演示页 |
| [demo/typography-demo-en.html](demo/typography-demo-en.html) | 适合纯英文内容的排版演示页 |

#### 效果截图

| 文件 | 说明 |
|---|---|
| [demo/apprentice-cn.png](demo/apprentice-cn.png) | Apprentice：中文 / 中英混排效果截图 |
| [demo/apprentice-code.png](demo/apprentice-code.png) | Apprentice：代码区效果截图 |
| [demo/apprentice-en.png](demo/apprentice-en.png) | Apprentice：英文效果截图 |
| [demo/codex-cn.png](demo/codex-cn.png) | Codex：中文 / 中英混排效果截图 |
| [demo/codex-code.png](demo/codex-code.png) | Codex：代码区效果截图 |
| [demo/codex-en.png](demo/codex-en.png) | Codex：英文效果截图 |
| [demo/feuilleton-cn.png](demo/feuilleton-cn.png) | Feuilleton：中文 / 中英混排效果截图 |
| [demo/feuilleton-code.png](demo/feuilleton-code.png) | Feuilleton：代码区效果截图 |
| [demo/feuileton-en.png](demo/feuileton-en.png) | Feuilleton：英文效果截图 |

### 前置要求

- [Obsidian](https://obsidian.md) v1.0+
- 社区主题：**[AnuPpuccin](https://github.com/AnubisNekwormo/AnuPpuccin)**
- 社区插件：**[Style Settings](https://github.com/mgmeyers/obsidian-style-settings)**

### 安装步骤

#### 第一步：安装主题与插件

1. 在 Obsidian 中打开 **设置 → 外观**，搜索并启用 **AnuPpuccin** 主题。
2. 打开 **设置 → 第三方插件**，安装并启用 **Style Settings**。
3. 打开 **设置 → Style Settings**，点击右上角的 **Import（导入）** 按钮。
4. 根据你要使用的方案，打开以下文件之一：
   - `snippets/antique-vellum-apprentice.json`
   - `snippets/antique-vellum-codex.json`
   - `snippets/antique-vellum-feuilleton.json`
   复制该文件的全部内容，粘贴到导入对话框中。这样会应用基础 palette、布局参数、标题设定，以及 preset 级字体栈配置。

#### 第二步：安装字体

本主题会使用若干字体，其中一部分 **macOS 不自带**，需要通过 Font Book 手动安装。

对于 **Option 1: Apprentice**，`QiushuiShotai` 必须安装为**系统字体**。对应 snippet 通过 `local("QiushuiShotai")` 调用它，而不是从 vault 内部的 `.ttf` 文件直接加载。如果你想得到当前推荐的西文气质，也建议安装 `Crimson Pro` 或 `Crimson Text`；否则 Apprentice 会回退到 `Iowan Old Style` / `Constantia` / `Palatino`。如果你想得到当前这版代码区效果，也请安装 `Operator Mono`，让 snippet 能命中 `Operator Mono Book` / `Operator Mono Book Italic`；否则 Apprentice 会回退到 `Menlo` / `Consolas`。如果你想得到当前这版文章标题效果，也请安装 `Hiragino Sans GB`，让 inline title 能切换到这颗展示字体。

对于 **Option 3: Feuilleton**，如果你想得到当前这版预期中的中文正文气质，请将 `HYCuFangSongJ` 安装为**系统字体**。对应 snippet 会匹配 Font Book 暴露出的本地 family / display / PostScript 名称，而不是从 vault 内的 `.ttf` 直接加载。

##### 可能需要手动安装的字体

| 字体 | 当前用途 | 下载地址 |
|---|---|---|
| `Operator Mono` | Apprentice 首选代码字体（`Operator Mono Book` / Book Italic） | 请根据本地授权与安装情况确认 |
| `Consolas`, `Input Mono`, `Berkeley Mono`, `Menlo` | Feuilleton 代码字体（更冷静、更稳、更具编辑部感的等宽路线） | `Consolas` 作为首选；`Input Mono` / `Berkeley Mono` 需本地安装；`Menlo` 作为后备 |
| `Crimson Pro`, `Crimson Text` | Apprentice 主西文字体 | [Google Fonts](https://fonts.google.com/specimen/Crimson+Pro) |
| `QiushuiShotai` | Apprentice 主 CJK 字体来源 | 详见字体作者发布渠道 |
| `Hiragino Sans GB` | Apprentice 文章标题字体 | 请根据本地授权与安装情况确认 |
| `HYCuFangSongJ` | Feuilleton 主 CJK 字体来源 | 详见字体作者发布渠道 |
| `Noto Serif SC`, `Source Han Serif SC` | Codex 中文正文字体栈；Feuilleton 中文后备字体 | [Google Fonts](https://fonts.google.com/noto/specimen/Noto+Serif+SC) |

##### macOS 上通常可直接使用的字体

| 字体 | 当前用途 | 备注 |
|---|---|---|
| `Iowan Old Style`, `Palatino`, `Palatino Linotype` | Apprentice 西文后备字体 | macOS 原生内置 / 本地常见可用 |
| `Menlo` | Apprentice 代码后备字体 | macOS 原生内置 |
| `STKaiti`, `Kaiti SC`, `KaiTi` | Apprentice CJK 后备字体 | 取决于系统环境 |
| `Hiragino Sans GB` | Apprentice 文章标题字体族 | 建议本地确认 |
| `Charter`, `Bitstream Charter` | Codex 西文正文 | 取决于系统环境，建议本地确认 |
| `EB Garamond` | Feuilleton 西文正文 | 建议安装（更修长、更古典的杂志质感） |
| `Songti SC` | Feuilleton 中文后备字体 | macOS 原生内置 |
| `Didot`, `Bodoni MT` | Feuilleton inline title | macOS 原生内置 |

##### 如何验证字体是否可用

可以打开 [demo/typography-demo-zh.html](demo/typography-demo-zh.html) 来检查中英混排 / 中文内容，或打开 [demo/typography-demo-en.html](demo/typography-demo-en.html) 来检查纯英文内容。
也可以结合上方效果截图对照当前渲染结果。
这些演示页**不会**加载网络字体，而是完全依赖本地系统字体，因此能较准确地反映 Obsidian 中的真实渲染结果。
如果 demo 页面与参考截图在字体气质、字宽、标题形态或代码区样式上差异很大，通常说明相关字体没有正常安装，当前渲染已经回退到后备字体。

#### 第三步：启用对应的 CSS snippet

##### 为什么这一步是必需的

1. **字体分流与字体覆盖** —— snippet 会注入各方案真实使用的字体栈，以及局部标题字体行为。目前，**Option 1: Apprentice 与 Option 3: Feuilleton 都明确通过 `@font-face` + `unicode-range` 实现了 CJK 语种隔离**；Option 2: Codex 仍然依赖普通 font stack。
2. **方案级排版微调** —— snippet 负责控制正文行高、字距、inline title 尺寸，以及代码区处理方式。不同方案的微排版行为并不相同。
3. **共享阅读界面语言** —— snippet 同时应用共享的文章 panel、更深一层的 code block 表面、安静的分割线，以及轻度强化的表格结构。浅色模式 palette 本身由导入的 preset JSON 提供。

一句话概括：**preset 决定 palette、标题字重、布局参数与 rainbow 行为；snippet 决定字体覆盖、局部排版行为与阅读界面层次。**

##### 操作步骤

1. 将对应方案的 snippet 复制到 vault 的 `.obsidian/snippets/` 目录：
   - Option 1: `snippets/antique-vellum-apprentice.css`
   - Option 2: `snippets/antique-vellum-codex.css`
   - Option 3: `snippets/antique-vellum-feuilleton.css`
2. 在 Obsidian 中打开 **设置 → 外观**，滚动到 **CSS snippets** 区域。
3. 点击刷新，然后**只启用**与你导入 preset 相对应的那一个 snippet。
4. 如果使用 Option 1，请确认 `QiushuiShotai` 已作为系统字体安装，否则会回退到下一个可用字体。

### 许可

MIT

---

## English

> An eye-friendly Obsidian theme preset — warm vellum tones, watercolor-style accents, and a comfortable long-form reading experience.
>
> This project prioritizes the best possible visual result over font-install convenience. Some fonts may need to be searched for, downloaded, and installed manually.

### What's Included

#### Presets

| File | Description |
|---|---|
| [snippets/antique-vellum-apprentice.json](snippets/antique-vellum-apprentice.json) | Option 1: Apprentice |
| [snippets/antique-vellum-apprentice.css](snippets/antique-vellum-apprentice.css) | Core snippet for Option 1: font isolation, font overrides, and typography tuning |
| [snippets/antique-vellum-codex.json](snippets/antique-vellum-codex.json) | Option 2: Codex |
| [snippets/antique-vellum-codex.css](snippets/antique-vellum-codex.css) | Core snippet for Option 2: font overrides, typography tuning, and reading-surface layer |
| [snippets/antique-vellum-feuilleton.json](snippets/antique-vellum-feuilleton.json) | Option 3: Feuilleton |
| [snippets/antique-vellum-feuilleton.css](snippets/antique-vellum-feuilleton.css) | Core snippet for Option 3: font overrides, typography tuning, and reading-surface layer |

#### Docs

| File | Description |
|---|---|
| [design-system-rationale.md](design-system-rationale.md) | Design rationale and current implementation notes |
| [typography-rationale-and-spec.md](typography-rationale-and-spec.md) | Typography system and implementation details |

#### Demo

| File | Description |
|---|---|
| [demo/typography-demo-zh.html](demo/typography-demo-zh.html) | Typography demo for bilingual / Chinese-heavy content |
| [demo/typography-demo-en.html](demo/typography-demo-en.html) | Typography demo for English-only content |

#### Reference screenshots

| File | Description |
|---|---|
| [demo/apprentice-cn.png](demo/apprentice-cn.png) | Apprentice: Chinese / bilingual rendering reference |
| [demo/apprentice-code.png](demo/apprentice-code.png) | Apprentice: code-area rendering reference |
| [demo/apprentice-en.png](demo/apprentice-en.png) | Apprentice: English rendering reference |
| [demo/codex-cn.png](demo/codex-cn.png) | Codex: Chinese / bilingual rendering reference |
| [demo/codex-code.png](demo/codex-code.png) | Codex: code-area rendering reference |
| [demo/codex-en.png](demo/codex-en.png) | Codex: English rendering reference |
| [demo/feuilleton-cn.png](demo/feuilleton-cn.png) | Feuilleton: Chinese / bilingual rendering reference |
| [demo/feuilleton-code.png](demo/feuilleton-code.png) | Feuilleton: code-area rendering reference |
| [demo/feuileton-en.png](demo/feuileton-en.png) | Feuilleton: English rendering reference |

### Prerequisites

- [Obsidian](https://obsidian.md) v1.0+
- Community theme: **[AnuPpuccin](https://github.com/AnubisNekwormo/AnuPpuccin)**
- Community plugin: **[Style Settings](https://github.com/mgmeyers/obsidian-style-settings)**

### Installation

#### Step 1: Install the theme and plugin

1. In Obsidian, open **Settings → Appearance**, search for **AnuPpuccin**, and enable it.
2. Open **Settings → Community plugins**, install **Style Settings**, and enable it.
3. Open **Settings → Style Settings**, then click the **Import** button in the upper-right corner.
4. Depending on the preset you want to use, open one of the following files:
   - `snippets/antique-vellum-apprentice.json`
   - `snippets/antique-vellum-codex.json`
   - `snippets/antique-vellum-feuilleton.json`
   Copy the entire file contents and paste them into the import dialog. This applies the base palette, layout values, heading settings, and preset-level font stack configuration.

#### Step 2: Install fonts

This theme uses several fonts. Some of them are **not bundled with macOS** and should be installed manually through Font Book.

For **Option 1: Apprentice**, `QiushuiShotai` must be installed as a **system font**. The snippet references it via `local("QiushuiShotai")`; it is not loaded from a local `.ttf` file inside the vault. For the intended Latin text look, also install `Crimson Pro` or `Crimson Text`; otherwise Apprentice falls back to `Iowan Old Style` / `Constantia` / `Palatino`. For the current code-area design, install `Operator Mono` so the snippet can resolve `Operator Mono Book` / `Operator Mono Book Italic`; otherwise Apprentice falls back to `Menlo` / `Consolas`. If you want the current article-title look, also install `Hiragino Sans GB` so inline titles can switch to that display face.

For **Option 3: Feuilleton**, install `HYCuFangSongJ` as a **system font** if you want the intended CJK body-text look. The snippet matches the local family / display / PostScript names exposed by Font Book rather than loading a local `.ttf` from the vault.

##### Fonts that may require manual installation

| Font | Current use | Download |
|---|---|---|
| `Operator Mono` | Apprentice preferred code font (`Operator Mono Book` / Book Italic) | Verify local licensing / installation |
| `Consolas`, `Input Mono`, `Berkeley Mono`, `Menlo` | Feuilleton code font (cooler, steadier editorial monospace route) | `Consolas` is now preferred; install `Input Mono` / `Berkeley Mono` locally; `Menlo` acts as fallback |
| `Crimson Pro`, `Crimson Text` | Apprentice primary Latin text | [Google Fonts](https://fonts.google.com/specimen/Crimson+Pro) |
| `QiushuiShotai` | Apprentice primary CJK source | Check the font author's release channel |
| `Hiragino Sans GB` | Apprentice inline-title font | Verify local licensing / installation |
| `HYCuFangSongJ` | Feuilleton primary CJK source | Check the font author's release channel |
| `Noto Serif SC`, `Source Han Serif SC` | Codex CJK text stack; Feuilleton CJK fallback | [Google Fonts](https://fonts.google.com/noto/specimen/Noto+Serif+SC) |

##### Fonts typically available on macOS

| Font | Current use | Notes |
|---|---|---|
| `Iowan Old Style`, `Palatino`, `Palatino Linotype` | Apprentice Latin fallback | Built into macOS / commonly available locally |
| `Menlo` | Apprentice code fallback | Built into macOS |
| `STKaiti`, `Kaiti SC`, `KaiTi` | Apprentice CJK fallback | Depends on system environment |
| `Hiragino Sans GB` | Apprentice inline-title family | Verify local installation |
| `Charter`, `Bitstream Charter` | Codex Latin text | Depends on system environment; verify locally |
| `EB Garamond` | Feuilleton Latin text | Recommended install (more slender, classical magazine tone) |
| `Songti SC` | Feuilleton CJK fallback | Built into macOS |
| `Didot`, `Bodoni MT` | Feuilleton inline title | Built into macOS |

##### How to verify font availability

Open [demo/typography-demo-zh.html](demo/typography-demo-zh.html) for bilingual / Chinese-heavy content, or [demo/typography-demo-en.html](demo/typography-demo-en.html) for English-only content.
You can also compare the current rendering against the reference screenshots above.
These demo pages do **not** load web fonts; they rely entirely on locally installed system fonts, so they closely reflect the actual Obsidian rendering environment.
If the demo pages look significantly different from the reference screenshots in font tone, glyph width, heading shapes, or code-area styling, the required fonts are usually not installed correctly and the rendering has fallen back to substitute fonts.

#### Step 3: Enable the matching CSS snippet

##### Why this step is required

1. **Font routing and font overrides** — The snippet injects the actual font stack and local title font behavior for each preset. At the moment, **Option 1: Apprentice and Option 3: Feuilleton explicitly implement CJK font isolation via `@font-face` + `unicode-range`**; Option 2: Codex still relies on a normal font stack.
2. **Preset-specific typography tuning** — The snippet controls line height, letter spacing, inline title sizing, and code-area treatment. Not every preset uses the same microtypography behavior.
3. **Shared reading-surface language** — The snippet also applies the shared article panel, deeper code-block surface, quiet dividers, and lightly strengthened table structure. The light-mode palette itself is provided by the imported preset JSON.

In short: **the preset controls palette, heading weights, layout values, and rainbow behavior; the snippet controls font overrides, local typography behavior, and reading-surface layering.**

##### Steps

1. Copy the matching snippet into your vault's `.obsidian/snippets/` folder:
   - Option 1: `snippets/antique-vellum-apprentice.css`
   - Option 2: `snippets/antique-vellum-codex.css`
   - Option 3: `snippets/antique-vellum-feuilleton.css`
2. In Obsidian, open **Settings → Appearance** and scroll down to **CSS snippets**.
3. Click refresh, then enable **only** the snippet that matches your imported preset.
4. If you use Option 1, make sure `QiushuiShotai` is installed as a system font; otherwise it will fall back to the next available font.

### License

MIT
