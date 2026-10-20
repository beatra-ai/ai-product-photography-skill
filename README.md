# AI Product Photography Skill

English | [简体中文](./README.zh-CN.md) | [日本語](./README.ja.md)

> 👉 See also [Ecommerce Product Images Skill](https://github.com/beatra-ai/ecommerce-product-images-skill)

Turn a real product photo into studio-quality ecommerce images and lifestyle scenes, from inside Claude Code, Cursor, Codex, Windsurf, Cline, or OpenClaw.

> [!IMPORTANT]
> Rendering needs a [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-product-photography-skill) account and uses credits. The skill itself is free to install.

| Question | Answer |
| --- | --- |
| **What it does** | Transform a real product photo into a studio-quality ecommerce image, lifestyle scene, or marketplace-ready hero shot with clean backgrounds, professional lighting, and composition guided by confirmed product details. |
| **Models** | Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, MiniMax Image 01 Live |
| **Requirements** | Python 3.10+ and an agent that loads `SKILL.md` |
| **Cost** | Free to install. Each render uses credits on your Beatra account, and paid steps run only when you ask for that exact render or approve its card. |
| **Works with** | Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="A cluttered kitchen-counter phone snapshot of a fictional rosehip face oil, OLUNEA (itself AI-generated as the demo input), turned into a white-background studio listing image with the label text and bottle shape unchanged. AI-generated with Beatra."></p>

*A cluttered kitchen-counter phone snapshot of a fictional rosehip face oil, OLUNEA (itself AI-generated as the demo input), turned into a white-background studio listing image with the label text and bottle shape unchanged. AI-generated with Beatra.*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`product-photo-studio`](skills/product-photo-studio) | [SKILL.md](skills/product-photo-studio/SKILL.md) | 0.2.9 |

This repository is published automatically from [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/product-photo-studio). Report issues there.

## Install

With the [`skills`](https://skills.sh) CLI:

```bash
npx skills add beatra-ai/ai-product-photography-skill
```

With the GitHub CLI:

```bash
gh skill install beatra-ai/ai-product-photography-skill product-photo-studio
```

Or clone this repository and copy `skills/product-photo-studio` into `~/.claude/skills/` for Claude Code,
`~/.cursor/skills/` for Cursor, `~/.agents/skills/` for Codex, `~/.codeium/windsurf/skills/` for Windsurf,
`~/.cline/skills/` for Cline, or `~/.openclaw/skills/` for OpenClaw.

Or paste this into your agent:

```text
Install the product-photo-studio skill from https://github.com/beatra-ai/ai-product-photography-skill (folder skills/product-photo-studio), then follow its SKILL.md to connect my Beatra account.
```

## Examples

<p align="center"><img src="assets/demo-2.webp" width="800" alt="The same OLUNEA bottle from the phone snapshot placed in a marble bathroom-vanity lifestyle scene with soft window light, label and shape kept as in the source. AI-generated with Beatra."></p>

*The same OLUNEA bottle from the phone snapshot placed in a marble bathroom-vanity lifestyle scene with soft window light, label and shape kept as in the source. AI-generated with Beatra.*

Ask your agent:

```text
Using ./olunea-counter.jpg as the product reference, place the same dropper bottle on a marble bathroom vanity with soft window light for a social post. Keep the label text, shape and color exactly as in the photo.
```

Prompt:

```text
Professional lifestyle product photo for social media. Image 1 is the product reference: the dropper bottle standing on the counter. Match its shape, color, label, label text, and proportions closely, and keep the label text exactly as it appears in Image 1. Leave out the kitchen counter and all other objects from Image 1. Place only the bottle upright on a white marble bathroom vanity, facing the camera, slightly right of center, with a folded linen hand towel and a small sprig of dried rose hips softly out of focus in the background, smaller than the bottle. Soft diffused window light from the left, warm neutral color temperature, gentle highlight on the glass, shallow depth of field with the bottle sharp and the background soft, natural contact shadow falling to the right, clean product edges, consistent lighting direction, no halo or fringe. No added text, logos, or watermarks.
```

## Technical Specifications & Output Limits

As of 2026-10-18. Live list: https://docs.beatra.ai/en/docs/models

- **Uploads** — up to 100 MB per file; the per-model input limits below also apply
- **Image to image** — 10 models (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, MiniMax Image 01 Live); PNG; up to 4 images per request; canvas up to 16.8 MP
  - 16.8 MP (4K tier): GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2 (1 image per request)
  - Input images: up to 4 per request, 10–20 MB each; BMP, GIF, JPEG, PNG, TIFF, WEBP
- **Image editing** — 6 models (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro); PNG; up to 4 images per request; canvas up to 4.2 MP
  - 4.2 MP (2K tier): Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro (up to 4 images per request)
  - Input images: up to 4 per request, 10–20 MB each; BMP, GIF, JPEG, PNG, TIFF, WEBP

## Why use Beatra instead of calling model APIs directly

- **One account for every model this skill uses** — Image to image 10; Image editing 6 (Qwen Image 2.0 Fast, Qwen Image 3.0, Qwen Image 3.0 Pro, Wan Image 2.7 Fast, Qwen Image 2.0 Pro, Wan Image 2.7 Pro, GPT Image 2.5 Flare, GPT Image 2.5 Sunburst, GPT Image 2, MiniMax Image 01 Live) (as of 2026-10-18), behind one Beatra sign-in; no keys from individual model providers to manage.
- **You decide what gets paid for** — Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate.
- **Direction before rendering** — the skill plans, directs, and reviews the work, then renders it on Beatra.
- **Files you can verify** — every file under `skills/` matches the release archive on cdn.beatra.ai byte for byte, checked by SHA-256 before each push.
- **Updates you control** — no self-updater; update with the tool you installed it with.
- **Runs in your agent** — Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw.

## What you get

- **The source product as the visual anchor** — Carry the confirmed shape, color, label, proportions, materials, and included pieces from the source photo into each new background or scene.
- **Marketplace-oriented backgrounds** — Create pure-white Amazon main images, clean Taobao listings, consistent Shopify catalogs, and lifestyle social posts from the same product photo.
- **Scene and lifestyle staging** — Place the product in a contextual scene—kitchen counter, wooden table, marble shelf, or seasonal backdrop—with matching lighting and natural shadow.

## Use cases

- **Marketplace main images** — Clean white-background product photos prepared for Amazon, Taobao, Rakuten, and Shopify listing contexts.
- **Lifestyle and contextual scenes** — Product-in-use images that show the item in a real-world setting, building buyer confidence and desire.
- **Ad and campaign visuals** — Premium hero shots with dramatic lighting and studio-gradient backgrounds for paid ads and landing pages.
- **Social media product posts** — Eye-catching product visuals for Instagram, TikTok, and Pinterest that stop the scroll and drive clicks.

## FAQ

### How do source details guide the new image?

The source photo and confirmed shape, color, label, proportions, materials, and included pieces become the visual reference for the new background and lighting.

### Can I create clean white-background listing images?

Yes. Share the target marketplace and its current image guidance, then choose a clean white background, even studio lighting, and suitable product framing.

### Can I place my product in a lifestyle scene?

Yes. Describe the desired setting—a kitchen counter, wooden table, bathroom shelf, or seasonal backdrop—and the product is placed in that scene with matching lighting and natural shadow.

### Can I refine a specific area of a selected photo?

Yes. Use the selected image as the base and name the reflection, shadow, edge, color, or small defect that needs a focused adjustment.

## Updates and security

Since the 2026-10 release, this skill contains no self-updater: it runs only the
files you installed and never replaces them on its own. Update it with the tool
you installed it with — `npx skills update product-photo-studio` or `gh skill update product-photo-studio`.
Details: `references/updates-and-security.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.

## Links

- Website — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-product-photography-skill
- Docs — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-product-photography-skill
- Console — https://console.beatra.ai
- For AI agents — https://beatra.ai/llms.txt (index) · https://beatra.ai/llms-full.txt (every skill in one file)
