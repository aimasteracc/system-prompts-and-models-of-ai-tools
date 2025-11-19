# Steering Rules作成プロンプト / Steering Rules Creation Prompt

このプロンプトを使用して、KIROプロジェクト用のSteering Rulesを簡単に作成できます。

---

## プロンプトテンプレート / Prompt Template

```
以下のプロジェクト情報を基に、KIRO用のSteering Rulesを作成してください。
Steering Rulesは `.kiro/steering/` ディレクトリに以下の3つのファイルとして作成します:

1. product.md - プロダクト概要
2. structure.md - プロジェクト構造
3. tech.md - 技術スタック

【プロジェクト情報】
プロジェクト名: [プロジェクト名を入力]
プロジェクトパス: [プロジェクトのルートパスを入力]
プログラミング言語: [Java/Python/TypeScript等を入力]
主要フレームワーク: [Spring/React/Django等を入力]

【プロジェクトの目的・ドメイン】
[プロジェクトが何を目的としているか、どのドメインに属するかを説明]

【主要機能】
- [機能1]
- [機能2]
- [機能3]

【技術スタック詳細】
ビルドツール: [Maven/Gradle/npm等]
主要ライブラリ: [使用している主要なライブラリとバージョン]
データベース: [Oracle/PostgreSQL/MySQL等]
その他の技術: [Redis/MQ/その他]

【プロジェクト構造の特徴】
[ディレクトリ構造、パッケージ命名規則、アーキテクチャパターン等]

【追加情報】
[その他、開発者が知っておくべき重要な情報]
```

---

## 各ファイルの作成ガイドライン

### 1. product.md (プロダクト概要)

**目的**: プロジェクトの全体像、ビジネスドメイン、主要機能を説明

**必須セクション**:
- `# Product Overview` - プロジェクトの概要説明
- `## Domain` または `## Purpose` - ドメインや目的
- `## Key Features` または `## Key Characteristics` - 主要機能・特徴

**推奨内容**:
- プロジェクトの背景（マイグレーション、新規開発等）
- ビジネスドメインの説明
- システムの役割と責任範囲
- 主要な業務機能のリスト
- 命名規則（プログラム名、モジュール名等）

**Front-matter設定**:
```markdown
---
inclusion: always
---
```

**記述例**:
```markdown
---
inclusion: always
---

# Product Overview

This is a [プロジェクトタイプ] for [組織名]. The project [目的の説明].

## Domain

[ドメインの詳細説明]

## Key Features

- [機能1の説明]
- [機能2の説明]
- [機能3の説明]

## [プログラム/モジュール] Naming Convention

[命名規則の説明]
Examples: [具体例]
```

---

### 2. structure.md (プロジェクト構造)

**目的**: ディレクトリ構造、パッケージ構成、アーキテクチャパターンを説明

**必須セクション**:
- `# Project Structure` - プロジェクト構造の概要
- `## Source Organization` または `## Directory Organization` - ソース構成
- `## Key Architectural Patterns` - アーキテクチャパターン

**推奨内容**:
- ディレクトリツリー図（コードブロック形式）
- パッケージ命名規則
- 各ディレクトリの役割説明
- ファイル配置ルール
- テストコードの構成
- リソースファイルの配置
- アーキテクチャレイヤーの説明

**Front-matter設定**:
```markdown
---
inclusion: always
---
```

**記述例**:
```markdown
---
inclusion: always
---

# Project Structure

## Root Package

`[ベースパッケージ名]` - [説明]

## Source Organization

### Main Source (`src/main/java`)

```
[パッケージ名]/
├── [サブパッケージ1]/     # [説明]
│   ├── [クラス1].java
│   └── [クラス2].java
├── [サブパッケージ2]/     # [説明]
└── [サブパッケージ3]/     # [説明]
```

### Test Source (`src/test/java`)

```
[テスト構成の説明]
```

## Key Architectural Patterns

### [パターン名1]

[パターンの説明]

### [パターン名2]

[パターンの説明]

## Naming Conventions

- **[カテゴリ1]**: [命名規則]
- **[カテゴリ2]**: [命名規則]
```

---

### 3. tech.md (技術スタック)

**目的**: 使用技術、ビルドコマンド、開発環境の情報を提供

**必須セクション**:
- `# Technology Stack` - 技術スタックの概要
- `## Build System` - ビルドシステム
- `## Core Frameworks` または `## Core Technologies` - 主要フレームワーク
- `## Common Commands` - よく使うコマンド

**推奨内容**:
- ビルドツールとバージョン
- フレームワークとライブラリ（バージョン付き）
- データベース情報
- テストフレームワーク
- よく使うビルド・テストコマンド
- CI/CD設定情報
- 環境固有の設定

**Front-matter設定**:
```markdown
---
inclusion: always
---
```

**記述例**:
```markdown
---
inclusion: always
---

# Technology Stack

## Build System

- **[ビルドツール名] [バージョン]** - [説明]
- Java [バージョン] source/target compatibility

## Core Frameworks

- **[フレームワーク名] [バージョン]** - [説明]
- **[ライブラリ名] [バージョン]** - [説明]

## Database

- **[DB名] [バージョン]** - [説明]

## Testing

- **[テストフレームワーク] [バージョン]** - [説明]

## Common Commands

### Build and Package
```bash
[ビルドコマンド]
```

### Run Tests
```bash
[テストコマンド]
```

### [その他のコマンド]
```bash
[コマンド]
```

## Configuration Notes

- [設定に関する重要な注意事項]
```

---

## 実践例: Javaマイグレーションプロジェクト

### 入力プロンプト例

```
以下のプロジェクト情報を基に、KIRO用のSteering Rulesを作成してください。

【プロジェクト情報】
プロジェクト名: legacy-migration-project
プロジェクトパス: /path/to/project
プログラミング言語: Java
主要フレームワーク: Spring Framework, Custom Migration Framework

【プロジェクトの目的・ドメイン】
政府機関向けレガシーシステムのCOBOL-to-Javaマイグレーションプロジェクト。
レガシーメインフレームCOBOLプログラムを移行フレームワークを使用してJavaに移行。
業務管理システム。

【主要機能】
- データ計算とシミュレーションのバッチ処理
- 各種計算処理
- 業務関連文書のレポート生成
- 業務記録と処理管理のためのデータベース操作

【技術スタック詳細】
ビルドツール: Maven 3.6+
主要ライブラリ:
  - Custom Migration Framework 2.x (COBOL移行フレームワーク)
  - Spring Framework 5.3+
  - MyBatis 3.5+
  - Lombok 1.18+
データベース: Oracle 19c
その他の技術: JUnit 5.7+, DBUnit 2.7+, Application Server

【プロジェクト構造の特徴】
- ベースパッケージ: com.example.organization.system
- BPRモジュール (bpr/) とマイグレーションコード (migration/) の2層構造
- プログラム命名: XXX0AXXX形式
- 各プログラムにConstants、InputInfo、Base、Mainクラスを含む
- テストデータはCSV形式でtest/resources/data配下に配置

【追加情報】
- 文字エンコーディング: UTF-8
- Java 11互換性
- レガシーデータ構造をアノテーションで定義
- DBUnitを使用したデータベース駆動テスト
```

---

## ベストプラクティス

### 1. Front-matterの使用

すべてのSteering Rulesファイルには以下のfront-matterを含めます:

```markdown
---
inclusion: always
---
```

これにより、ファイルが常にKIROのコンテキストに含まれます。

### 2. 多言語プロジェクトの場合

- 特定言語のコメントや用語が多い場合は、その旨を明記
- 重要な専門用語には説明を併記
- 例: "業務管理 (business management)"

### 3. バージョン情報の記載

技術スタックには必ずバージョン番号を含めます:
- 良い例: `Spring Framework 5.3.34`
- 悪い例: `Spring Framework`

### 4. コマンド例の提供

tech.mdには実際に使用するコマンドを記載:
```bash
mvn clean install
mvn test
mvn package -DskipTests
```

### 5. 構造図の活用

structure.mdではディレクトリツリーを視覚的に表現:
```
src/
├── main/
│   ├── java/
│   └── resources/
└── test/
    ├── java/
    └── resources/
```

### 6. 具体例の提供

命名規則やパターンには必ず具体例を含めます:
- プログラム名: `XXX0A100`, `XXX0A200`
- パッケージ名: `com.example.organization.module.XXX0A100`

---

## チェックリスト

Steering Rules作成時の確認項目:

### product.md
- [ ] プロジェクトの目的が明確に記載されている
- [ ] ドメイン/業務領域が説明されている
- [ ] 主要機能がリストアップされている
- [ ] 命名規則（該当する場合）が説明されている
- [ ] front-matterが含まれている

### structure.md
- [ ] ディレクトリ構造が視覚的に表現されている
- [ ] パッケージ命名規則が説明されている
- [ ] 主要なアーキテクチャパターンが記載されている
- [ ] テストコードの配置が説明されている
- [ ] front-matterが含まれている

### tech.md
- [ ] ビルドシステムとバージョンが記載されている
- [ ] 主要フレームワーク・ライブラリがバージョン付きで列挙されている
- [ ] データベース情報が含まれている
- [ ] よく使うコマンドが記載されている
- [ ] テストフレームワークが説明されている
- [ ] front-matterが含まれている

---

## トラブルシューティング

### Q: プロジェクト情報が不足している場合は？

A: 以下の順序で情報を収集してください:
1. `pom.xml` または `build.gradle` を確認（技術スタック）
2. `README.md` を確認（プロジェクト概要）
3. ソースコードのパッケージ構造を確認（構造情報）
4. 主要なクラスファイルを確認（アーキテクチャパターン）

### Q: 複数のサブプロジェクトがある場合は？

A: 各サブプロジェクトに個別の `.kiro/steering/` を作成するか、
共通部分をルートに配置し、サブプロジェクト固有の情報を各ディレクトリに配置します。

### Q: マイグレーションプロジェクトの場合の注意点は？

A: 以下を明記してください:
- 移行元の技術（例: COBOL）
- 移行先の技術（例: Java + Spring）
- 使用している移行フレームワーク（例: Majalis）
- レガシーコードとの互換性に関する情報

---

## 参考リンク

- KIRO Steering機能: プロジェクトの `.kiro/steering/*.md` に配置
- Front-matter設定: `inclusion: always` で常時読み込み
- ファイル参照: `#[[file:<relative_file_name>]]` で他ファイルを参照可能

---

## まとめ

このプロンプトテンプレートを使用することで:
1. 一貫性のあるSteering Rulesを作成できます
2. プロジェクトの重要情報を体系的に整理できます
3. 新しい開発者のオンボーディングが容易になります
4. KIROがプロジェクトコンテキストを正確に理解できます

プロジェクト情報を上記のテンプレートに従って入力し、KIROに渡すだけで、
適切なSteering Rulesが自動生成されます。
