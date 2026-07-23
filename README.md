# note収益化 運営チーム（Claude Code版）

note アカウント [smart_ai_log](https://note.com/smart_ai_log) の収益化（有料記事・有料マガジン）を、
Claude Code のサブエージェント／スキルだけで運営するためのリポジトリです。

詳細な運用方針は [`CLAUDE.md`](./CLAUDE.md) を参照してください。

## 使い方（クイックスタート）

1. まず `content/strategy.md` の「ブランド定義」欄を、実際のアカウントのテーマ・トンマナに合わせて記入する
2. `/note-weekly-plan` で企画カレンダーを作る
3. `/note-new-article` で1本ずつ記事を企画→執筆→編集する（下書きは `content/drafts/` に出力される）
4. 完成した下書きを note に手動で投稿する（note には投稿APIがないため自動投稿はできません）
5. `/note-promote` でSNS告知文を作る
6. 投稿後の反応（PV・スキ・購入数など）を `content/strategy.md` の「実績・学び」に記録し、
   次の企画・価格設定に活かす

## ディレクトリ構成

```
.claude/agents/    企画・執筆・編集・グロース戦略の4サブエージェント
.claude/skills/    note-new-article / note-weekly-plan / note-promote の3ワークフロー
content/strategy.md   収益化戦略（ブランド定義・価格・マガジン設計・実績）
content/calendar.md    企画カレンダー
content/templates/     記事テンプレート
content/drafts/        下書き
content/published/     投稿済み記事のアーカイブ
```

## その他の運営チーム

- YouTubeチャンネル「R×R camper's channel」の運営チーム: [`youtube/CLAUDE.md`](./youtube/CLAUDE.md)
