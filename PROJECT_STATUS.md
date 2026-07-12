# shogu-app PROJECT STATUS

## 正本
- ソースコード: GitHubリポジトリ `hiro-saitoh-sr/shogu-app`
- 本番公開先: GitHub Pages
- 連携データ: task-appと共通のFirebase Realtime Database

## Git状態
- 対象ブランチ: `main`
- 整備開始時の基準コミット: `07e5c58`
- 2026-07-11確認時点で `origin/main` と同期済み（ahead 0 / behind 0）

## 現在の実装状況
- 処遇改善加算、ベースアップ評価料、臨時の補助金の計画書・実績報告書を管理
- ステータス管理、提出期日一括設定、顧問先マスタ管理を実装
- Firebase Authenticationの許可対象は業務用アカウント2件（Firebase側で管理）
- CodexとClaude Codeは対等な開発担当であり、共通Git手順と競合停止ルールを適用する

## Firebaseパス
### 実装上確認済み
- `shogu/masters`
- `shogu/deliveries/shoguPlan`
- `shogu/deliveries/shoguReport`
- `shogu/deliveries/rinjiPlan`
- `shogu/deliveries/rinjiReport`
- `shogu/deliveries/baseupPlan`
- `shogu/deliveries/baseupInterim`
- `shogu/deliveries/baseupReport`
- 各deliveries配下の `status`

### 実データ未確認
- 上記パスは `index.html` の参照・書込実装から確認したもので、Firebase上の実データの存在・内容・件数は未確認
- 旧文書にあった `shogu/customers` と `shogu/cases` は現行実装から確認できず、実データも未確認

## 直近の変更
- AI引継ぎ資料とGit除外設定を整備
- `.claude/` 全体ではなく端末固有のローカル設定だけを除外
- Claude CodeとCodexを対等な開発担当として明記
- Git作業開始・終了、競合停止、利用者承認ルールを統一

## デプロイ・公開状況
- 公開URL: https://hiro-saitoh-sr.github.io/shogu-app/
- 今回は管理文書とGit除外設定のみを変更し、アプリ、Firebase、GAS、データは変更しない

## 検証結果
- `git fetch origin` 後、作業開始時にローカルと `origin/main` の一致を確認
- Firebaseパスを現行 `index.html` から静的確認
- 文書変更のためアプリ動作確認は対象外

## 既知の課題
- Firebaseの実データ構造と件数は未確認

## NEXT_ACTION
- 次回作業開始時に `git fetch origin`、指示文書、Git状態を再確認する
- Firebase関連の変更時は、実データ確認と影響範囲整理を先に行う

## 最終更新
- 最終更新AI: Codex
- 最終更新日時: 2026-07-13（日本時間）
