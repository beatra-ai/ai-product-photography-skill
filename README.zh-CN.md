# AI Product Photography Skill

[English](./README.md) | 简体中文

把真实商品照片变成影棚级电商主图和场景图，在 Claude Code、Codex 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 将真实产品照片转化为影棚级电商主图、场景图或面向市场平台的高清商品图，支持换背景、改善光效和搭建场景，并延续已确认的商品外观特征。 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Codex、OpenClaw |

| Skill | Entry point | Version |
| --- | --- | --- |
| [`product-photo-studio`](skills/product-photo-studio) | [SKILL.md](skills/product-photo-studio/SKILL.md) | 0.2.0 |

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

也可以克隆本仓库，把 `skills/product-photo-studio` 复制到 `~/.claude/skills/`（Claude Code）、`~/.agents/skills/`（Codex）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-product-photography-skill 安装 product-photo-studio skill（目录 skills/product-photo-studio），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

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

## 更新

安装后的 skill 每天最多检查一次新版本，替换前先校验官方归档，任何一步失败都不会动你已安装的版本。
随时可以关闭，见 skill 内的 `references/automatic-updates-and-safety.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。
