# AI Product Photography Skill

[English](./README.md) | 简体中文 | [日本語](./README.ja.md)

> 👉 也看看 [Ecommerce Product Images Skill](https://github.com/beatra-ai/ecommerce-product-images-skill)

把真实商品照片变成电商棚拍图和场景图，在 Claude Code、Cursor、Codex、Windsurf、Cline 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-product-photography-skill) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 将真实产品照片转化为影棚级电商主图、场景图或面向市场平台的高清商品图，支持换背景、改善光效和搭建场景，并延续已确认的商品外观特征。 |
| **底层模型** | Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、MiniMax Image 01 Live |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="一张杂乱厨房台面上的手机随手拍（虚构品牌 OLUNEA 玫瑰果面部精华油，这张输入图本身也是为演示 AI 生成的），被转成白底棚拍商品主图，标签文字和瓶身形状保持不变。由 Beatra AI 生成。"></p>

*一张杂乱厨房台面上的手机随手拍（虚构品牌 OLUNEA 玫瑰果面部精华油，这张输入图本身也是为演示 AI 生成的），被转成白底棚拍商品主图，标签文字和瓶身形状保持不变。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`product-photo-studio`](skills/product-photo-studio) | [SKILL.md](skills/product-photo-studio/SKILL.md) | 0.2.9 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/product-photo-studio) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/ai-product-photography-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/ai-product-photography-skill product-photo-studio
```

也可以克隆本仓库，把 `skills/product-photo-studio` 复制到 `~/.claude/skills/`（Claude Code）、`~/.cursor/skills/`（Cursor）、`~/.agents/skills/`（Codex）、`~/.codeium/windsurf/skills/`（Windsurf）、`~/.cline/skills/`（Cline）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-product-photography-skill 安装 product-photo-studio skill（目录 skills/product-photo-studio），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/demo-2.webp" width="800" alt="把手机随手拍里的同一瓶 OLUNEA 放进大理石浴室台面的生活场景，窗边柔光，标签与瓶形与原图一致。由 Beatra AI 生成。"></p>

*把手机随手拍里的同一瓶 OLUNEA 放进大理石浴室台面的生活场景，窗边柔光，标签与瓶形与原图一致。由 Beatra AI 生成。*

在你的 Agent 里这样说：

```text
以 ./olunea-counter.jpg 为商品参考，把这瓶滴管精华放到有柔和窗光的大理石浴室台面上，做一张社交媒体用的场景图。标签文字、瓶形和颜色要和原照片完全一致。
```

提示词：

```text
Professional lifestyle product photo for social media. Image 1 is the product reference: the dropper bottle standing on the counter. Match its shape, color, label, label text, and proportions closely, and keep the label text exactly as it appears in Image 1. Leave out the kitchen counter and all other objects from Image 1. Place only the bottle upright on a white marble bathroom vanity, facing the camera, slightly right of center, with a folded linen hand towel and a small sprig of dried rose hips softly out of focus in the background, smaller than the bottle. Soft diffused window light from the left, warm neutral color temperature, gentle highlight on the glass, shallow depth of field with the bottle sharp and the background soft, natural contact shadow falling to the right, clean product edges, consistent lighting direction, no halo or fringe. No added text, logos, or watermarks.
```

## 技术规格与输出限制

截至 2026-10-18。实时列表：https://docs.beatra.ai/zh/docs/models

- **上传** — 单个文件最大 100 MB；同时适用下方各模型的输入限制
- **图生图** — 10 个模型（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、MiniMax Image 01 Live）；PNG；单次最多 4 张；画布最大 16.8 MP
  - 16.8 MP（4K 档）：GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2（单次 1 张）
  - 输入图片：单次最多 4 张，每张 10–20 MB；BMP、GIF、JPEG、PNG、TIFF、WEBP
- **图片编辑** — 6 个模型（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro）；PNG；单次最多 4 张；画布最大 4.2 MP
  - 4.2 MP（2K 档）：Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro（单次最多 4 张）
  - 输入图片：单次最多 4 张，每张 10–20 MB；BMP、GIF、JPEG、PNG、TIFF、WEBP

## 为什么用 Beatra，而不是直接调用模型 API

- **一个账号用到本 skill 的全部模型** — 图生图 10；图片编辑 6（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、MiniMax Image 01 Live）（截至 2026-10-18），一次 Beatra 登录即可使用，不必分别管理各家模型的 key。
- **花不花钱由你决定** — 只有你明确要求这次生成，或批准显示实时积分估算的确认卡后才会付费。
- **先策划，再生成** — skill 先帮你规划、指导和检查，再在 Beatra 上生成。
- **文件可以核验** — `skills/` 下的每个文件都与 cdn.beatra.ai 上的发布归档逐字节一致，每次推送前用 SHA-256 校验。
- **更新由你掌控** — 不含自更新程序；用安装时的工具更新。
- **在你的 Agent 里运行** — Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw。

## 你能得到什么

- **以真实商品为视觉锚点** — 把原图中已确认的形状、颜色、标签、比例、材质和包装内容延续到新的背景与场景中。
- **面向平台场景的背景** — 从同一张产品照片制作亚马逊纯白主图、淘宝干净主图、Shopify 统一目录图和社交媒体生活场景图。
- **场景化与生活化** — 将产品放入真实使用场景——厨房台面、木桌、大理石层架或季节背景——搭配一致的光效和自然阴影。

## 适用场景

- **平台主图** — 为亚马逊、淘宝、乐天和 Shopify 等上架场景准备干净的白底商品图。
- **生活场景图** — 产品在使用场景中的图片，展示真实使用环境，增强买家信心和购买欲。
- **广告与活动视觉** — 高级英雄图，搭配戏剧化光效和影棚渐变背景，用于付费广告和落地页。
- **社交媒体商品图** — 为 Instagram、TikTok 和小红书打造吸睛的商品视觉，提升点击和转化。

## 常见问题

### 商品原图如何引导新图片？

原图以及已确认的形状、颜色、标签、比例、材质和包装内容，会成为新背景与光效的视觉参考。

### 能制作干净的白底上架图吗？

可以。提供目标平台及其当前图片指引，再选择干净白底、均匀影棚光效和合适的商品构图。

### 能把产品放到生活场景里吗？

可以。描述期望的场景——厨房台面、木桌、浴室置物架或季节背景——产品就会被放入该场景，搭配一致光效和自然阴影。

### 能精修选定图片的某个区域吗？

可以。以选定图片为基础，说明需要聚焦调整的反光、阴影、边缘、色彩或小瑕疵。

## 更新与安全

自 2026 年 10 月的版本起，本 skill 不再包含自更新程序：它只运行你安装的文件，从不自行替换。
请用安装时的工具更新——`npx skills update product-photo-studio` 或 `gh skill update product-photo-studio`。
详见 skill 内的 `references/updates-and-security.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。

## 相关链接

- 官网 — https://www.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-product-photography-skill
- 文档 — https://docs.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-product-photography-skill
- 控制台 — https://console.beatra.cn
- 给 AI Agent 读的说明 — https://www.beatra.cn/llms.txt（索引）· https://www.beatra.cn/llms-full.txt（全部 skill 合成一个文件）

- 微信小程序 — 国内用户微信扫码使用

<img src="assets/beatra-mini-program-qr.jpg" alt="Beatra 微信小程序码" width="160">
