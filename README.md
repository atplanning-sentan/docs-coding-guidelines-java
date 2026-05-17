# ☕ ATP Java コーディング規約

[![ATP | Java コーディング規約](https://img.shields.io/badge/ATP-Java_コーディング規約-8e1b46?style=flat-square)](https://www.atp.co.jp/)
[![AI レビュー対応](https://img.shields.io/badge/AIレビュー-対応-8e1b46?style=flat-square)](https://github.com/atplanning-sentan/docs-coding-guidelines-java/blob/main/java/AI_PROMPT.md)

**株式会社エーティ・プランニング**  
先端技術本部  
コンサルティング＆アーキテクトグループ（CAG）

本リポジトリは、先端技術本部が制定した Java コーディング規約（原典: [Javaコーディング規約.docx](docs/original/Javaコーディング規約.docx)）を単一の参照源として管理し、Pull Request レビューおよび AI によるコードレビューで利用できるよう整備したものです。

> [!NOTE]
> **公開範囲**  
> 社内・社外を問わず、Java でソフトウェアを開発する者向けに公開しています。

> [!CAUTION]
> **免責**  
> 本リポジトリの内容は、先端技術本部が現時点の best effort で提供するものです。  
> 内容の完全性・正確性・最新性、および特定目的への適合性を保証するものではありません。
>
> 利用・参照は各自の責任で行い、プロジェクトの要件に応じて判断してください。
>
> 規約の変更は [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md) に従います。

## 📦 含まれるもの

### 規約・レビュー

- 規約（Markdown版）: [java/CODING_RULES.md](java/CODING_RULES.md)
- レビュー判定: [java/REVIEW_CHECKLIST.md](java/REVIEW_CHECKLIST.md)
- OK/NG例: [java/PATTERNS.md](java/PATTERNS.md), [java/NG_PATTERNS.md](java/NG_PATTERNS.md)

### AIレビュー

- プロンプト: [java/AI_PROMPT.md](java/AI_PROMPT.md)
- 利用ルール: [java/AI_RULES.md](java/AI_RULES.md)

### ドキュメント・原典

- 原典（Word）: [docs/original/Javaコーディング規約.docx](docs/original/Javaコーディング規約.docx)
- 規約から参照する画像: [docs/images/](docs/images/)
- 変更履歴（詳細）: [docs/CHANGELOG.md](docs/CHANGELOG.md)（要約は本ファイル末尾の [改定履歴](#改定履歴)）
- 規約の変更手順: [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md)

### GitHub 運用

- PRテンプレート: [.github/pull_request_template.md](.github/pull_request_template.md)
- 再利用可能な品質チェック CI: [.github/workflows/reusable-java-quality.yml](.github/workflows/reusable-java-quality.yml)

### ビルド連携

- 品質設定一式（Checkstyle / SpotBugs テンプレ / markdownlint）: [templates/quality/](templates/quality/)
- Maven 品質プラグイン設定（完全版）: [templates/quality/maven/quality-plugins.xml](templates/quality/maven/quality-plugins.xml)
- Maven 品質プラグイン（簡易・レガシー）: [templates/maven/quality-plugins.xml](templates/maven/quality-plugins.xml)

## 📖 使い方

### 1. 規約を読む

[java/CODING_RULES.md](java/CODING_RULES.md)（具体例は [java/PATTERNS.md](java/PATTERNS.md) / [java/NG_PATTERNS.md](java/NG_PATTERNS.md)）

### 2. PRを出す

[.github/pull_request_template.md](.github/pull_request_template.md) に従い、[java/CODING_RULES.md](java/CODING_RULES.md) と [java/REVIEW_CHECKLIST.md](java/REVIEW_CHECKLIST.md) で確認する

### 3. AIレビューする

手順の正本: [java/AI_PROMPT.md](java/AI_PROMPT.md)

**レビュー対象**は本リポジトリではなく、**AIエディタ**で開いている **Java アプリケーション** の `src/main/java`（PR の差分は見ない。ルール試験・ベースライン監査用）。

**前提**として [java/AI_RULES.md](java/AI_RULES.md)・[java/CODING_RULES.md](java/CODING_RULES.md)・[java/REVIEW_CHECKLIST.md](java/REVIEW_CHECKLIST.md) を読ませること（任意: [java/PATTERNS.md](java/PATTERNS.md) / [java/NG_PATTERNS.md](java/NG_PATTERNS.md)）。

#### 方式A: URL（clone 不要）

① レビュー対象の Java プロジェクトを AIエディタで開く

② AIチャットに、次の **raw URL**（`blob` ではなく `raw.githubusercontent.com`）を読ませる

| 文書 | raw URL |
|------|---------|
| AI_PROMPT | https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/AI_PROMPT.md |
| AI_RULES | https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/AI_RULES.md |
| CODING_RULES | https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/CODING_RULES.md |
| REVIEW_CHECKLIST | https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/REVIEW_CHECKLIST.md |

**送信例（そのまま送信してよい）:**

```text
次の raw URL を読み、AI_PROMPT.md の手順に従い、
現在のワークスペースの src/main/java を一括レビューしてください。
PR・git 差分・src/test は対象外です。

https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/AI_PROMPT.md
https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/AI_RULES.md
https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/CODING_RULES.md
https://raw.githubusercontent.com/atplanning-sentan/docs-coding-guidelines-java/main/java/REVIEW_CHECKLIST.md
```

③ バージョンを固定する場合は、上記 URL の `main` をコミット SHA に差し替える

④ 任意ファイル（PATTERNS / NG_PATTERNS）や詳細手順: [AI_PROMPT.md](java/AI_PROMPT.md) 付録「方式A」

#### 方式B: clone + @ 参照（推奨・安定）

① 本リポジトリを clone する

② レビュー対象プロジェクトを AIエディタで開き、必要ならワークスペースに本リポジトリを追加する

③ AIチャットで次を @ 添付する（パスは clone 先に合わせる）

- `java/AI_PROMPT.md`
- `java/AI_RULES.md`
- `java/CODING_RULES.md`
- `java/REVIEW_CHECKLIST.md`
- （任意）`java/PATTERNS.md` / `java/NG_PATTERNS.md`

④ 続けて次を送る

```text
AI_PROMPT.md に従い、本ワークスペースの src/main/java を一括レビューしてください。
PR・git 差分・src/test は対象外。【出力】§1〜§5 と REVIEW_CHECKLIST 全項目の表を出してください。
```

⑤ チームで規約版を揃える場合は tag または commit を checkout する

### 4. （任意）CI・Maven

他リポジトリから [.github/workflows/reusable-java-quality.yml](.github/workflows/reusable-java-quality.yml) を `workflow_call` で呼び出す。`templates/quality/` をコピーし、[templates/quality/maven/quality-plugins.xml](templates/quality/maven/quality-plugins.xml) を `pom.xml` に取り込む。

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
└── templates/
    ├── quality/          # Checkstyle / SpotBugs / markdownlint（推奨）
    └── maven/            # 品質プラグイン簡易テンプレ（レガシー）
```

---

## 📜 改定履歴

| 日付 | 内容 |
|---|---|
| 2026-05-15 | 新規制定（原典 docx の Markdown 化、レビュー・AI・CI テンプレート一式）。README・`CODING_RULES.md` を実構成に合わせて整備 |
| 2026-05-18 | 企業公開向け README 整備（日本語タイトル・正式社名・先端技術本部 CAG 表記・公開範囲/免責の Alert、AI レビュー起動手順、使い方の見出し構成と ① 手順）。`CODING_RULES.md` の説明文を文単位改行に整理。`AI_PROMPT.md` に起動テンプレート付録を追加 |
| 2026-05-18 | `templates/quality/` 追加（Checkstyle / SpotBugs / markdownlint / Maven 連携） |
