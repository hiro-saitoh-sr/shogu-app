# shogu-app プロジェクト

## プロジェクト概要
社会保険労務士齊藤事務所の処遇改善加算タスク管理システム。
処遇改善加算・ベースアップ評価料・臨時の補助金の計画書・実績報告書の管理を行う。

## 公開URL・リポジトリ
- 公開URL: https://hiro-saitoh-sr.github.io/shogu-app/
- リポジトリ: https://github.com/hiro-saitoh-sr/shogu-app

## 技術スタック
- HTML/CSS/JavaScript（フレームワークなし）
- Firebase Realtime Database
- Firebase Authentication（メール認証）

## Firebase設定
- プロジェクトID: task-app-493716（task-appと共通）
- リージョン: asia-southeast1
- DB URL: https://task-app-493716-default-rtdb.asia-southeast1.firebasedatabase.app
- ログイン許可アカウント: 業務用アカウント2件（Firebase側で管理）

## データ構造（Firebase Realtime Database）
- `shogu/` : shogu-app専用データ
- `shogu/customers`: 処遇改善加算対象の顧問先マスタ
- `shogu/cases`: 処遇改善加算関連の案件データ

## task-appとの連携
- task-appの顧問先マスタで「処遇改善加算チェック」をONにすると、
  shogu-appの顧問先マスタに自動反映される
- 連携項目: No・顧問先名・代表者名・担当者名・メール
- 処遇改善加算チェックをOFFにしても自動削除はしない（手動対応）

## 開発方針
- Claude CodeとCodexを対等な開発担当として使用する
- どちらが作業しても引き継げるよう、Git履歴・本ファイル・CLAUDE.md・PROJECT_STATUS.mdを正本として確認する
- 修正後は必ず `git add . && git commit && git push` を実行
- コミットメッセージは日本語で「feat: 」「fix: 」等のプレフィックスを付ける
- ステップごとに確認しながら進める

## 注意事項
- 事務所のサービスとして提供している業務のシステム、既存データへの影響に注意
- Firebase Rulesは変更しない（cases・mastersは.read: true、書き込みは認証必須）
- 変更時はブラウザで動作確認してから push
- 個人名は使用しない（「正社員さん」「パートさん」で統一）

## 主な機能
- 処遇改善加算計画書・実績報告書の管理
- ベースアップ評価料の管理
- 臨時の補助金計画書の管理
- ステータス管理（未着手→依頼中→収集済→集計完了→納品済）
- 提出期日一括設定機能

## 実装済み機能
- 令和7年度計画書データインポート（80件）
- 令和8年度臨時の補助金計画書インポート
- 顧問先マスタ管理

## 今後の予定
- 令和8年度計画書データインポート

## 関連プロジェクト
- task-app: 社労士業務タスク管理システム（顧問先マスタが連携）
- estimate-contract-app: 見積書・契約書作成アプリ
