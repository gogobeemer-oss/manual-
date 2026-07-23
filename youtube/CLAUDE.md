# R×R camper's channel 運営チーム（Claude Code版）

このディレクトリは、YouTubeチャンネル「R×R camper's channel」の成長と運用効率化を担う
「AI運営チーム」の設定です。note収益化チーム（リポジトリルートの `CLAUDE.md`）と同様に、
役割ごとに専門化したサブエージェントが企画・タイトル/サムネ・構成/台本・SEOを分担します。

## 運営方針（前提）

- 課題: 視聴回数は好調（年間17.6万回）だが、チャンネル登録への転換が弱い
  （年間獲得 +519人、前年比30%減少）
- 目標: 既存の「高評価・高視聴維持率」を維持したまま、新規視聴者を
  「チャンネル登録者」に変える動線（CTA・サムネイル・シリーズ化）を強化する
- 詳細なアナリティクス・キラーコンテンツ分析は `youtube/channel-strategy.md` を参照

## チーム構成（サブエージェント）

| エージェント | ファイル | 役割 |
|---|---|---|
| Lead Strategist | `.claude/agents/yt-lead-strategist.md` | 全体戦略、アナリティクス分析、CVR（登録率）改善案 |
| Thumbnail & Title Specialist | `.claude/agents/yt-thumbnail-title.md` | タイトル案、サムネイル構成・配色指示 |
| Video Script & Storyboard Director | `.claude/agents/yt-script-director.md` | チャプター構成、オープニングフック、CTA挿入設計 |
| SEO & Metadata Optimizer | `.claude/agents/yt-seo-metadata.md` | 概要欄、タグ、ハッシュタグ、タイムスタンプ、翻訳 |

## よく使うワークフロー（スキル）

- `/yt-new-video-plan` : 新動画の企画・素材テーマを入力すると、4エージェントを連携させ
  「現状評価→タイトル案→サムネ案→構成/CTA設計→SEOテキスト」の企画書を
  `youtube/video-plans/` に出力する

## ディレクトリ構成

```
youtube/
  CLAUDE.md            このファイル（チーム概要・運用方針）
  channel-strategy.md   チャンネルアナリティクス・キラーコンテンツ分析・実績記録
  video-plans/          動画企画書（/yt-new-video-plan の出力先）
  published/            公開済み動画の実績アーカイブ（振り返り用）
```

## 運用ルール

- 新動画の企画は `/yt-new-video-plan` から開始する
  （Lead Strategist → Thumbnail & Title → Script Director → SEO Optimizerの順で連携）
- 企画書には必ず「どのキラーコンテンツ（ドキュメンタリー・育成系／車・ギア・DIY系／長尺・旅・
  チャレンジ系）の派生・応用か」を明記し、チャンネル登録への動線（CTA設計）を含めること
- 公開後の実績（登録者転換率・視聴維持率など）は本人から聞き取り、
  `youtube/channel-strategy.md` の「実績・学び」セクションに記録して次の企画に反映する
