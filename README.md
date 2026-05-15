# ☕ docs-coding-guidelines-java
本リポジトリは、ATP先端技術本部が制定した Java コーディング規約（原典: [Javaコーディング規約.docx](docs/original/Javaコーディング規約.docx)）を単一の参照源として管理し、Pull Request レビューおよび AI によるコードレビューで利用できるよう整備したものです。

## 📦 含まれるもの

### 📋 規約・レビュー
- 規約（完全版・Markdown化）: [java/CODING_RULES.md](java/CODING_RULES.md)
- レビュー判定: [java/REVIEW_CHECKLIST.md](java/REVIEW_CHECKLIST.md)
- OK/NG例: [java/PATTERNS.md](java/PATTERNS.md), [java/NG_PATTERNS.md](java/NG_PATTERNS.md)

### 🤖 AIレビュー
- プロンプト: [java/AI_PROMPT.md](java/AI_PROMPT.md)
- 利用ルール: [java/AI_RULES.md](java/AI_RULES.md)

### 📄 ドキュメント・原典
- 原典（Word）: [docs/original/Javaコーディング規約.docx](docs/original/Javaコーディング規約.docx)
- 規約から参照する画像: [docs/images/](docs/images/)
- 変更履歴（詳細）: [docs/CHANGELOG.md](docs/CHANGELOG.md)（要約は本ファイル末尾の [改定履歴](#改定履歴)）
- 規約の変更手順: [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md)

### 🐙 GitHub運用
- PRテンプレート: [.github/pull_request_template.md](.github/pull_request_template.md)
- 再利用可能な品質チェック CI: [.github/workflows/reusable-java-quality.yml](.github/workflows/reusable-java-quality.yml)

### 🏗️ ビルド連携
- Maven品質プラグイン設定テンプレート: [templates/maven/quality-plugins.xml](templates/maven/quality-plugins.xml)

## 📖 使い方

1. 📋 **規約を読む**: [java/CODING_RULES.md](java/CODING_RULES.md)（具体例は [java/PATTERNS.md](java/PATTERNS.md) / [java/NG_PATTERNS.md](java/NG_PATTERNS.md)）
2. 🔀 **PRを出す**: [.github/pull_request_template.md](.github/pull_request_template.md) に従い、[java/CODING_RULES.md](java/CODING_RULES.md) と [java/REVIEW_CHECKLIST.md](java/REVIEW_CHECKLIST.md) で確認する
3. 🤖 **AIレビューする**: [java/AI_PROMPT.md](java/AI_PROMPT.md) をレビューツールに貼り付ける（[java/AI_RULES.md](java/AI_RULES.md) と上記規約・チェックリストが前提）
4. ⚙️ **（任意）CI・Maven**: 他リポジトリから [.github/workflows/reusable-java-quality.yml](.github/workflows/reusable-java-quality.yml) を `workflow_call` で呼び出す。設定例は [templates/maven/quality-plugins.xml](templates/maven/quality-plugins.xml)

## 📁 ディレクトリ構成

```
.
├── java/                 # 規約・チェックリスト・AI用ドキュメント
├── docs/
│   ├── images/           # 規約から参照する図
│   ├── original/         # 原典 docx
│   ├── CHANGELOG.md
│   └── CONTRIBUTING.md   # 規約の変更手順
├── .github/
│   ├── pull_request_template.md
│   └── workflows/
└── templates/maven/      # 品質プラグイン設定のテンプレート
```

---

## 📜 改定履歴

| 日付 | 内容 |
|---|---|
| 2026-05-15 | 新規制定（原典 docx の Markdown 化、レビュー・AI・CI テンプレート一式） |
| 2026-05-15 | README を実フォルダ構成に合わせて更新、`CODING_RULES.md` にシャローコピー図をリンク |
