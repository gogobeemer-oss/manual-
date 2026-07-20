---
name: note-weekly-plan
description: note記事の週次/月次の企画カレンダーを作成・更新する。「今週の企画を立てて」「来月分の記事ネタを考えて」といった依頼で使う。
---

# note週次/月次企画カレンダー作成

`content-planner` サブエージェントを使い、`content/calendar.md` を作成・更新する。

## 手順

1. `content/calendar.md` を読み、既存の企画・直近の投稿実績を把握する
2. `content/strategy.md` のブランド定義・収益化方針を確認する
3. `content-planner` サブエージェントに、指定された期間（デフォルトは今後2週間）の企画リストを
   作らせる。各記事について以下を含める
   - 想定投稿日
   - タイトル案
   - 無料 / 有料の区分
   - 一言メモ（狙い・ネタ元）
4. 無料記事と有料記事の比率が `content/strategy.md` の方針から大きく外れていないか確認する
5. `content/calendar.md` を更新し、変更点をユーザーに要約して報告する

## 注意

- 既に `content/drafts/` や `content/published/` にある記事とテーマが重複しないようにする
- カレンダーはあくまで計画であり、都度 `/note-new-article` で実際の執筆に進む
