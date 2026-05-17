# Changelog

このファイルは変更の詳細を記録します。利用者向けの要約は [README.md](../README.md#改定履歴) の改定履歴を参照してください。

## 2026-05-18

### Changed
- `README.md` / `java/CODING_RULES.md`: 企業公開向け整理（日本語タイトル・CAG 表記、説明文の文単位改行、公開範囲/免責の Alert、バッジ、見出し・絵文字）。`CONTRIBUTING.md` に CODING_RULES 記載方針を追記
- `README.md`: AI レビュー起動手順（方式A raw URL・送信例 / 方式B clone + @・送信例）
- `README.md`: 「使い方」を H3（1〜4）/ H4（方式A/B）、手順を ①〜表記
- `java/AI_PROMPT.md`: 利用者向け起動テンプレート（URL / clone）を付録として追加

## 2026-05-15

### Changed
- `README.md`: 含まれるもの・使い方・ディレクトリ構成・改定履歴をリポジトリ実態に合わせて整備
- `java/CODING_RULES.md`: シャローコピー説明に `docs/images/image_01.png` をリンク

### Added（初回公開）
- 原典 docx（`docs/original/Javaコーディング規約.docx`）の完全 Markdown 化（`java/CODING_RULES.md`）
- レビュー判定（`java/REVIEW_CHECKLIST.md`）
- AIレビュー用ドキュメント（`java/AI_PROMPT.md`, `java/AI_RULES.md`）
- OK/NG例（`java/PATTERNS.md`, `java/NG_PATTERNS.md`）
- 規約用画像（`docs/images/`）
- PRテンプレート（`.github/pull_request_template.md`）
- 再利用可能な品質チェック CI（`.github/workflows/reusable-java-quality.yml`）
- Maven品質プラグイン設定テンプレート（`templates/maven/quality-plugins.xml`）
- 規約の変更手順（`docs/CONTRIBUTING.md`）
