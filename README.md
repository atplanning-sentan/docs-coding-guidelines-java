# docs-coding-guidelines-java

社内で共通利用する **Javaコーディング規約** と、レビュー運用（チェックリスト／PRテンプレート／AIレビュー手順）をまとめたリポジトリです。

## ねらい
- 規約を「読む」だけでなく、**レビューと自動チェック**で「守れる」状態にする
- 人間レビューとAIレビューの基準を揃え、**判断のブレを減らす**

## 収録物
- 規約本体: `java/CODING_RULES.md`
- レビュー判定: `java/REVIEW_CHECKLIST.md`
- AIレビュー: `java/AI_PROMPT.md` / `java/AI_RULES.md`
- OK/NG例: `java/PATTERNS.md` / `java/NG_PATTERNS.md`
- PRテンプレ: `.github/pull_request_template.md`
- 再利用テンプレ: `.github/workflows/reusable-java-quality.yml`
- Maven設定スニペット: `templates/maven/quality-plugins.xml`

## 使い方（推奨）
### 1) 規約の参照
- 開発者は `java/CODING_RULES.md` を参照し、実装方針を揃えます。

### 2) レビュー運用
- PR作成時にテンプレートが自動で表示されるため、`java/REVIEW_CHECKLIST.md` に沿って確認します。

### 3) AIレビュー
- `java/AI_PROMPT.md` をAIに渡してレビューさせます（出力形式が統一されます）。

### 4) 自動チェック（他リポジトリで再利用）
- このリポジトリは「ガイド」なので本体でチェックを回すのではなく、
  **再利用ワークフロー** `.github/workflows/reusable-java-quality.yml` を各プロジェクトで呼び出します。

## 更新運用
- 変更提案は `docs/CONTRIBUTING.md` を参照してください。
