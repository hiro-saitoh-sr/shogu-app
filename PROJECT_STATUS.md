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
- 臨時の補助金・実績報告ページのボタンを変更（「処遇改善加算からコピー」「ベースアップ評価料からコピー」を削除し、既存の「計画書からコピー」と同一動作のボタンを追加）。臨時の補助金・計画書ページのボタンは変更なし。
- 全タブ共通の絞り込みフィルターから「年度（すべて）」を削除し、「納品日（すべて）」（入力済み/未入力）を「ステータス（すべて）」（未着手/依頼中/収集済/集計完了/納品済、`statusMap`基準）に変更
- 対象は `DeliveryView` コンポーネント（処遇改善加算・ベースアップ評価料・臨時の補助金の全タブで共通利用）

## デプロイ・公開状況
- 公開URL: https://hiro-saitoh-sr.github.io/shogu-app/
- 今回は `index.html` のボタン・絞り込みフィルターのみ変更し、Firebase・GAS・データ構造は変更しない

## 検証結果
- `git fetch origin` 後、作業開始時にローカルと `origin/main` の一致を確認
- Babel（アプリ実行時と同じJSXトランスパイラ）で構文検証済み
- Chrome拡張機能が未接続のためブラウザでの実動作確認は未実施（利用者の承認を得て実施）

## 既知の課題
- Firebaseの実データ構造と件数は未確認
- 今回の変更について実ブラウザでの動作確認が未実施

## NEXT_ACTION
- 次回作業開始時に `git fetch origin`、指示文書、Git状態を再確認する
- Firebase関連の変更時は、実データ確認と影響範囲整理を先に行う
- 次回ログイン時に臨時の補助金・実績報告ページと全タブの絞り込みフィルターを実ブラウザで確認する

## 最終更新
- 最終更新AI: Claude Code
- 最終更新日時: 2026-07-24（日本時間）
