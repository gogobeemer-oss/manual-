# note収益化 運営チーム（Claude Code版）

このリポジトリは、note.com アカウント [smart_ai_log](https://note.com/smart_ai_log) を
収益化するための「運営チーム」を、Claude Code のサブエージェント／スキルだけで構成したものです。
人間のメンバーを雇う代わりに、役割ごとに専門化したサブエージェントが企画・執筆・編集・グロース戦略を分担します。

## 運営方針（前提）

- フェーズ: これから伸ばす段階（フォロワー・記事数はまだ少ない）
- 収益化の柱: 有料記事・有料マガジン（継続課金）
- 体制: 完全に Claude Code 上のエージェントで運営し、人間（アカウント運営者）は
  「最終確認・note への実際の投稿・SNS投稿」のみを行う（note には投稿API連携がないため、
  記事の生成物はこのリポジトリ内に Markdown として蓄積し、最終的に人間がコピー&ペーストで投稿する）
- ジャンル: アカウント名から推測して AI・生成AI活用ログ系を想定。実際のテーマ・トンマナは
  `content/strategy.md` の「ブランド定義」セクションを本人が埋めて確定させること

## チーム構成（サブエージェント）

| エージェント | ファイル | 役割 |
|---|---|---|
| 企画（プランナー） | `.claude/agents/content-planner.md` | ネタ出し、企画カレンダー作成、無料/有料の配分設計 |
| 執筆（ライター） | `.claude/agents/writer.md` | 記事の下書き作成 |
| 編集（エディター） | `.claude/agents/editor.md` | 校正、構成チェック、有料部分の壁（ここから先は有料）の設計 |
| グロース戦略 | `.claude/agents/growth-strategist.md` | 価格設定、マガジン設計、SNS導線、CTA最適化 |

## よく使うワークフロー（スキル）

- `/note-new-article` : 企画→執筆→編集を一気通貫で行い、`content/drafts/` に下書きを出力
- `/note-weekly-plan` : 1週間〜1ヶ月分の企画カレンダーを `content/calendar.md` に作成・更新
- `/note-promote` : 公開済み記事のX（旧Twitter）告知文・note内シェア文を生成

## ディレクトリ構成

```
content/
  strategy.md       収益化戦略（ブランド定義・価格・マガジン設計）
  calendar.md        企画カレンダー
  templates/          記事テンプレート
  drafts/             下書き（note投稿前）
  published/          投稿済み記事のアーカイブ（実績トラッキング用）
```

## 運用ルール

- 記事の新規作成は必ず `/note-new-article` から開始する（プランナー→ライター→エディターの順で連携）
- 有料記事は「無料パート（フック＋価値提示）」と「有料パート（具体的な手順・テンプレート・実例）」を
  エディターが明確に分離すること
- 下書きが完成したら `content/drafts/` から `content/published/` への移動は、実際に note に投稿した後に行う
- 収益化に関する数値目標・価格改定は `content/strategy.md` を更新して記録する

## 別の運営チーム（このリポジトリ内の別プロジェクト）

このリポジトリには、YouTubeチャンネル「R×R camper's channel」の運営チームも同居しています。
note チームとは独立した設定・ディレクトリ（`youtube/`）で運用するため、詳細は
[`youtube/CLAUDE.md`](./youtube/CLAUDE.md) を参照してください。
