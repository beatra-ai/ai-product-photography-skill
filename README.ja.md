# AI Product Photography Skill

[English](./README.md) | [简体中文](./README.zh-CN.md) | 日本語

> 👉 こちらもどうぞ [Ecommerce Product Images Skill](https://github.com/beatra-ai/ecommerce-product-images-skill)

実際の商品写真から、EC 向けのスタジオ写真とライフスタイルシーンを作成。Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw のどれからでもそのまま使えます。

> [!IMPORTANT]
> 生成には [Beatra](https://beatra.ai) アカウントが必要で、クレジットを消費します。スキル自体のインストールは無料です。

| 項目 | 内容 |
| --- | --- |
| **できること** | 実際の製品写真をスタジオ品質のEC画像、ライフスタイルシーン、または販売プラットフォーム向けのヒーローショットに変換。背景置換、照明改善、シーン演出に対応し、確認済みの商品外観を基準に構成します。 |
| **モデル** | Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、MiniMax Image 01 Live |
| **動作要件** | Python 3.10 以上と、`SKILL.md` を読み込めるエージェント |
| **費用** | インストールは無料。生成のたびに Beatra アカウントのクレジットを消費しますが、課金されるのは、その生成を明示的に依頼したとき、または確認カードを承認したときだけです。 |
| **対応エージェント** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/hero.webp" width="800" alt="散らかったキッチンカウンターでスマホ撮影した架空のローズヒップ美容オイル OLUNEA（入力画像自体もデモ用に AI 生成）を、ラベル文字とボトルの形を変えずに白背景の商品ページ用画像に変換。Beatra AI で生成。"></p>

*散らかったキッチンカウンターでスマホ撮影した架空のローズヒップ美容オイル OLUNEA（入力画像自体もデモ用に AI 生成）を、ラベル文字とボトルの形を変えずに白背景の商品ページ用画像に変換。Beatra AI で生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`product-photo-studio`](skills/product-photo-studio) | [SKILL.md](skills/product-photo-studio/SKILL.md) | 0.2.8 |

このリポジトリは [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/product-photo-studio) から自動的に公開されています。問題の報告はそちらへお願いします。

## インストール

[`skills`](https://skills.sh) CLI を使う場合：

```bash
npx skills add beatra-ai/ai-product-photography-skill
```

GitHub CLI を使う場合：

```bash
gh skill install beatra-ai/ai-product-photography-skill product-photo-studio
```

または、このリポジトリをクローンして `skills/product-photo-studio` を次の場所にコピーします：Claude Code は `~/.claude/skills/`、Cursor は `~/.cursor/skills/`、Codex は `~/.agents/skills/`、Windsurf は `~/.codeium/windsurf/skills/`、Cline は `~/.cline/skills/`、OpenClaw は `~/.openclaw/skills/`。

または、次の文をエージェントに貼り付けてください：

```text
https://github.com/beatra-ai/ai-product-photography-skill から product-photo-studio スキル（フォルダ skills/product-photo-studio）をインストールし、その SKILL.md に従って私の Beatra アカウントに接続してください。
```

## 作例

<p align="center"><img src="assets/demo-2.webp" width="800" alt="同じスマホ写真の OLUNEA ボトルを、窓からの柔らかい光が入る大理石の洗面台のライフスタイルシーンに配置。ラベルと形は元のまま。Beatra AI で生成。"></p>

*同じスマホ写真の OLUNEA ボトルを、窓からの柔らかい光が入る大理石の洗面台のライフスタイルシーンに配置。ラベルと形は元のまま。Beatra AI で生成。*

エージェントへの依頼例：

```text
./olunea-counter.jpg を商品の参考画像にして、同じスポイトボトルを柔らかい窓明かりの入る大理石の洗面台に置いた SNS 用の写真を作って。ラベルの文字、形、色は写真のままで。
```

プロンプト：

```text
Professional lifestyle product photo for social media. Image 1 is the product reference: the dropper bottle standing on the counter. Match its shape, color, label, label text, and proportions closely, and keep the label text exactly as it appears in Image 1. Leave out the kitchen counter and all other objects from Image 1. Place only the bottle upright on a white marble bathroom vanity, facing the camera, slightly right of center, with a folded linen hand towel and a small sprig of dried rose hips softly out of focus in the background, smaller than the bottle. Soft diffused window light from the left, warm neutral color temperature, gentle highlight on the glass, shallow depth of field with the bottle sharp and the background soft, natural contact shadow falling to the right, clean product edges, consistent lighting direction, no halo or fringe. No added text, logos, or watermarks.
```

## 技術仕様と出力上限

2026-10-18 時点。最新の一覧：https://docs.beatra.ai/ja/docs/models

- **アップロード** — 1 ファイルあたり最大 100 MB。下記の各モデルの入力制限も適用されます
- **画像から画像** — 10 モデル（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、MiniMax Image 01 Live）／PNG／1 リクエストあたり最大 4 枚／キャンバス最大 16.8 MP
  - 16.8 MP（4K ティア）：GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2（1 リクエストにつき 1 枚）
  - 入力画像：1 リクエストあたり最大 4 枚、各 10〜20 MB／BMP、GIF、JPEG、PNG、TIFF、WEBP
- **画像編集** — 6 モデル（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro）／PNG／1 リクエストあたり最大 4 枚／キャンバス最大 4.2 MP
  - 4.2 MP（2K ティア）：Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro（1 リクエストあたり最大 4 枚）
  - 入力画像：1 リクエストあたり最大 4 枚、各 10〜20 MB／BMP、GIF、JPEG、PNG、TIFF、WEBP

## 得られるもの

- **元の商品をビジュアルの基準に** — 元写真で確認した形状、色、ラベル、比率、素材、付属品を、新しい背景やシーンを作る際の基準にします。
- **販売プラットフォーム向けの背景** — 同じ製品写真からAmazon白背景メイン画像、楽天クリーンな商品画像、Shopify統一カタログ画像、SNSライフスタイル投稿を制作します。
- **シーンとライフスタイル演出** — 製品を文脈のあるシーンに配置します。キッチンカウンター、ウッドテーブル、大理石シェルフ、または季節の背景に、マッチする照明と自然なシャドウ。

## 活用シーン

- **マーケットプレイスメイン画像** — Amazon、楽天、Shopifyなどの掲載用途に合わせて準備する、クリーンな白背景の商品写真。
- **ライフスタイルシーン** — 製品が実使用環境にある画像。リアルな使用シーンでバイヤーの信頼と欲求を高める。
- **広告キャンペーンビジュアル** — ドラマチックな照明とスタジオグラデーション背景のプレミアムヒーローショット。広告やランディングページに最適です。
- **SNS向け商品投稿** — Instagram、TikTok、Pinterest向けの目を引く商品ビジュアル。スクロールを止め、クリックを促す。

## よくある質問

### 元の商品ディテールはどのように新しい画像へ反映されますか？

元写真で確認した形状、色、ラベル、比率、素材、付属品を、新しい背景と照明のビジュアルリファレンスとして使います。

### クリーンな白背景の商品画像は作れますか？

はい。掲載先と現在の画像ガイドを共有し、クリーンな白背景、均一なスタジオ照明、商品に合うフレーミングを指定できます。

### 製品をライフスタイルシーンに配置できますか？

はい。希望するシーン（キッチンカウンター、ウッドテーブル、バスルームシェルフ、季節の背景）をお伝えすると、製品がそのシーンに配置され、マッチする照明と自然なシャドウが追加されます。

### 選んだ画像の一部を重点的に調整できますか？

はい。選んだ画像をベースに、反射、影、エッジ、色、小さな傷など、調整したい箇所を指定できます。

## 更新とセキュリティ

2026 年 10 月のリリース以降、このスキルに自動更新機能はありません。インストールしたファイルだけを実行し、
自動的に置き換えることはありません。更新はインストールに使ったツール（`npx skills update product-photo-studio` または
`gh skill update product-photo-studio`）で行ってください。詳細はスキル内の `references/updates-and-security.md` を参照してください。

## ライセンス

[MIT-0](LICENSE)：商用を含め、自由に使用・改変・再配布できます。クレジット表記は不要です。ClawHub 上のこれらのスキルと同じ条件です。

## リンク

- ウェブサイト — https://beatra.ai
- ドキュメント — https://docs.beatra.ai
- コンソール — https://console.beatra.ai
- AI エージェント向け — https://beatra.ai/llms.txt（インデックス）· https://beatra.ai/llms-full.txt（全スキルを 1 ファイルに）
