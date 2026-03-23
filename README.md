# dev-rules

プロジェクト横断で使う開発ルールのテンプレート集。
AI（ChatGPT / Claude等）とターミナルから開発する際に、AIの記憶喪失とトークン消費に対応するためのルール体系。

## 使い方

1. 新規プロジェクト開始時に RULES_TEMPLATE.md をコピー
2. プロジェクトの docs/RULES.md として配置
3. {{プロジェクト名}} 等のプレースホルダーをプロジェクト固有の値に置換
4. docs/DECISIONS.md と docs/BACKLOG.md を空ファイルで作成
5. 必要に応じて templates/MODULE_INDEX_TEMPLATE.md をコピーし docs/MODULE_INDEX.md として配置
6. ファイルサイズ監視・技術的負債台帳にプロジェクトのファイルを記入

## ファイル構成

- RULES_TEMPLATE.md - 開発ルールテンプレート（本体）
- templates/HEARING_SHEET.md - ヒアリングシートテンプレート
- templates/MODULE_INDEX_TEMPLATE.md - モジュール索引テンプレート
- examples/postcraft_rules.md - PostCraftでの適用例
- README.md - このファイル

## 核心ルール

1. **コード即書き禁止**: 有識者議論とスコアリング8割以上で初めて着手
2. **コード保全**: 既存コードを許可なく変更・削除しない
3. **セッション開始プロトコル**: 毎回RULES.mdとDEVELOPMENT_PLAN.mdを再読み込み
4. **影響範囲宣言**: 変更前にBlast Radiusを宣言、5ファイル超は承認必須
5. **ハルシネーションガード**: ファイルパス・関数名は実在確認してから使用
6. **スコープロック**: 現タスク外の改善提案はBACKLOG.mdへ
7. **決定ログ**: 設計判断をDECISIONS.mdに記録、会話が消えても意図が残る
8. **トークン節約設計**: ドキュメント3層構造、画像/PDF直貼り回避、15-20ラリーでリセット
