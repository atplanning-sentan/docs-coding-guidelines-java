# ☕ docs-coding-guidelines-java

[![ATP](https://img.shields.io/badge/ATP-先端技術本部-8e1b46?style=flat-square)](https://www.atp.co.jp/)
![ATP Guide](https://img.shields.io/badge/ATP公式-Javaコーディング規約-8e1b46?style=flat-square)
![Guide](https://img.shields.io/badge/Guide-コーディング規約-8e1b46?style=flat-square)
![Standards](https://img.shields.io/badge/Standards-JavaCoding-8e1b46?style=flat-square)
![AI Review](https://img.shields.io/badge/AIレビュー対応-Yes-8e1b46?style=flat-square)


本リポジトリは、ATP先端技術本部が制定した Java コーディング規約（原典: [Javaコーディング規約.docx](docs/original/Javaコーディング規約.docx)）を単一の参照源として管理し、Pull Request レビューおよび AI によるコードレビューで利用できるよう整備したものです。

## 📦 含まれるもの

### 📋 規約・レビュー
- 規約（Markdown版）: [java/CODING_RULES.md](java/CODING_RULES.md)
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
3. 🤖 **AIレビューする**（手順の正本: [java/AI_PROMPT.md](java/AI_PROMPT.md)）

   **レビュー対象**は本リポジトリではなく、**AIエディタ**で開いている **Java アプリケーション** の `src/main/java`（PR の差分は見ない。ルール試験・ベースライン監査用）。

   **前提**として [java/AI_RULES.md](java/AI_RULES.md)・[java/CODING_RULES.md](java/CODING_RULES.md)・[java/REVIEW_CHECKLIST.md](java/REVIEW_CHECKLIST.md) を読ませること（任意: [java/PATTERNS.md](java/PATTERNS.md) / [java/NG_PATTERNS.md](java/NG_PATTERNS.md)）。

   #### 方式A: URL（clone 不要）

   1. レビュー対象の Java プロジェクトを AIエディタで開く
   2. AIチャットに、次の **raw URL**（`blob` ではなく `raw.githubusercontent.com`）を読ませる

      | 文書 | raw URL |
      |------|---------|
      | AI_PROMPT | https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/AI_PROMPT.md |
      | AI_RULES | https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/AI_RULES.md |
      | CODING_RULES | https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/CODING_RULES.md |
      | REVIEW_CHECKLIST | https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/REVIEW_CHECKLIST.md |

      **送信例（そのまま貼ってよい）:**

      ```text
      次の raw URL を読み、AI_PROMPT.md の手順に従い、
      現在のワークスペースの src/main/java を一括レビューしてください。
      PR・git 差分・src/test は対象外です。

      https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/AI_PROMPT.md
      https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/AI_RULES.md
      https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/CODING_RULES.md
      https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/REVIEW_CHECKLIST.md
      ```

   3. バージョンを固定する場合は、上記 URL の `main` をコミット SHA に差し替える
   4. 任意ファイル（PATTERNS / NG_PATTERNS）や詳細手順: [AI_PROMPT.md](java/AI_PROMPT.md) 付録「方式A」

   #### 方式B: clone + @ 参照（推奨・安定）

   1. 本リポジトリを clone する
   2. レビュー対象プロジェクトを AIエディタで開き、必要ならワークスペースに本リポジトリを追加する
   3. AIチャットで次を @ 添付する（パスは clone 先に合わせる）

      - `java/AI_PROMPT.md`
      - `java/AI_RULES.md`
      - `java/CODING_RULES.md`
      - `java/REVIEW_CHECKLIST.md`
      - （任意）`java/PATTERNS.md` / `java/NG_PATTERNS.md`

   4. 続けて次を送る

      ```text
      AI_PROMPT.md に従い、本ワークスペースの src/main/java を一括レビューしてください。
      PR・git 差分・src/test は対象外。【出力】§1〜§5 と REVIEW_CHECKLIST 全項目の表を出してください。
      ```

   5. チームで規約版を揃える場合は tag または commit を checkout する

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
| 2026-05-18 | README に AI レビュー起動手順（URL / clone）を追記、`AI_PROMPT.md` に起動テンプレート付録を追加 |
| 2026-05-18 | README 方式A に raw URL 一覧・チャット送信例を追記、方式B を @ 一覧・送信例で整理 |
