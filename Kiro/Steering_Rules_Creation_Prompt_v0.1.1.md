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

**重要**: 3つのファイルは、プロジェクトで使用されている主要言語（日本語、中国語、英語等）で記述してください。
技術用語やプロジェクト固有の用語は、後日LLMが検索できるよう、元の言語のまま記述することが重要です。

【プロジェクト情報】
プロジェクト名: [プロジェクト名を入力]
プロジェクトパス: [プロジェクトのルートパスを入力]
プログラミング言語: [Java/Python/TypeScript等を入力]
主要フレームワーク: [Spring/React/Django等を入力]
ドキュメント言語: [日本語/中国語/英語等、プロジェクトで主に使用されている言語を入力]

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

**言語**: プロジェクトで使用されている主要言語で記述（日本語プロジェクトなら日本語、中国語プロジェクトなら中国語等）

**必須セクション** (見出しはプロジェクトの言語で記述):
- 第1レベル見出し - プロジェクトの概要説明
  - 英語例: `# Product Overview`
  - 日本語例: `# プロダクト概要`
  - 中国語例: `# 产品概述`
- 第2レベル見出し - ドメインや目的
  - 英語例: `## Domain` または `## Purpose`
  - 日本語例: `## ドメイン` または `## 目的`
  - 中国語例: `## 领域` または `## 目的`
- 第2レベル見出し - 主要機能・特徴
  - 英語例: `## Key Features` または `## Key Characteristics`
  - 日本語例: `## 主要機能` または `## 主要特徴`
  - 中国語例: `## 主要功能` または `## 主要特性`

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

**記述例（日本語プロジェクトの場合）**:
```markdown
---
inclusion: always
---

# プロダクト概要

これは[組織名]向けの[プロジェクトタイプ]です。本プロジェクトは[目的の説明]。

## ドメイン

[ドメインの詳細説明]

## 主要機能

- [機能1の説明]
- [機能2の説明]
- [機能3の説明]

## プログラム命名規則

[命名規則の説明]
例: [具体例]
```

**記述例（英語プロジェクトの場合）**:
```markdown
---
inclusion: always
---

# Product Overview

This is a [project type] for [organization]. The project [purpose description].

## Domain

[Domain details]

## Key Features

- [Feature 1 description]
- [Feature 2 description]
- [Feature 3 description]

## Program Naming Convention

[Naming convention description]
Examples: [concrete examples]
```

---

### 2. structure.md (プロジェクト構造)

**目的**: ディレクトリ構造、パッケージ構成、アーキテクチャパターンを説明

**言語**: プロジェクトで使用されている主要言語で記述

**必須セクション** (見出しはプロジェクトの言語で記述):
- 第1レベル見出し - プロジェクト構造の概要
  - 英語例: `# Project Structure`
  - 日本語例: `# プロジェクト構造`
  - 中国語例: `# 项目结构`
- 第2レベル見出し - ソース構成
  - 英語例: `## Source Organization` または `## Directory Organization`
  - 日本語例: `## ソース構成` または `## ディレクトリ構成`
  - 中国語例: `## 源代码组织` または `## 目录组织`
- 第2レベル見出し - アーキテクチャパターン
  - 英語例: `## Key Architectural Patterns`
  - 日本語例: `## 主要アーキテクチャパターン`
  - 中国語例: `## 主要架构模式`

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

**記述例（日本語プロジェクトの場合）**:
```markdown
---
inclusion: always
---

# プロジェクト構造

## ルートパッケージ

`[ベースパッケージ名]` - [説明]

## ソース構成

### メインソース (`src/main/java`)

```
[パッケージ名]/
├── [サブパッケージ1]/     # [説明]
│   ├── [クラス1].java
│   └── [クラス2].java
├── [サブパッケージ2]/     # [説明]
└── [サブパッケージ3]/     # [説明]
```

### テストソース (`src/test/java`)

```
[テスト構成の説明]
```

## 主要アーキテクチャパターン

### [パターン名1]

[パターンの説明]

### [パターン名2]

[パターンの説明]

## 命名規則

- **[カテゴリ1]**: [命名規則]
- **[カテゴリ2]**: [命名規則]
```

**記述例（英語プロジェクトの場合）**:
```markdown
---
inclusion: always
---

# Project Structure

## Root Package

`[base package name]` - [description]

## Source Organization

### Main Source (`src/main/java`)

```
[package name]/
├── [subpackage1]/     # [description]
│   ├── [Class1].java
│   └── [Class2].java
├── [subpackage2]/     # [description]
└── [subpackage3]/     # [description]
```

### Test Source (`src/test/java`)

```
[test structure description]
```

## Key Architectural Patterns

### [Pattern Name 1]

[Pattern description]

### [Pattern Name 2]

[Pattern description]

## Naming Conventions

- **[Category 1]**: [naming rule]
- **[Category 2]**: [naming rule]
```

---

### 3. tech.md (技術スタック)

**目的**: 使用技術、ビルドコマンド、開発環境の情報を提供

**言語**: プロジェクトで使用されている主要言語で記述

**必須セクション** (見出しはプロジェクトの言語で記述):
- 第1レベル見出し - 技術スタックの概要
  - 英語例: `# Technology Stack`
  - 日本語例: `# 技術スタック`
  - 中国語例: `# 技术栈`
- 第2レベル見出し - ビルドシステム
  - 英語例: `## Build System`
  - 日本語例: `## ビルドシステム`
  - 中国語例: `## 构建系统`
- 第2レベル見出し - 主要フレームワーク
  - 英語例: `## Core Frameworks` または `## Core Technologies`
  - 日本語例: `## 主要フレームワーク` または `## コア技術`
  - 中国語例: `## 核心框架` または `## 核心技术`
- 第2レベル見出し - よく使うコマンド
  - 英語例: `## Common Commands`
  - 日本語例: `## よく使うコマンド`
  - 中国語例: `## 常用命令`

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

**記述例（日本語プロジェクトの場合）**:
```markdown
---
inclusion: always
---

# 技術スタック

## ビルドシステム

- **[ビルドツール名] [バージョン]** - [説明]
- Java [バージョン] source/target compatibility

## 主要フレームワーク

- **[フレームワーク名] [バージョン]** - [説明]
- **[ライブラリ名] [バージョン]** - [説明]

## データベース

- **[DB名] [バージョン]** - [説明]

## テスト

- **[テストフレームワーク] [バージョン]** - [説明]

## よく使うコマンド

### ビルドとパッケージング
```bash
[ビルドコマンド]
```

### テスト実行
```bash
[テストコマンド]
```

### [その他のコマンド]
```bash
[コマンド]
```

## 設定に関する注意事項

- [設定に関する重要な注意事項]
```

**記述例（英語プロジェクトの場合）**:
```markdown
---
inclusion: always
---

# Technology Stack

## Build System

- **[Build Tool Name] [Version]** - [description]
- Java [Version] source/target compatibility

## Core Frameworks

- **[Framework Name] [Version]** - [description]
- **[Library Name] [Version]** - [description]

## Database

- **[DB Name] [Version]** - [description]

## Testing

- **[Test Framework] [Version]** - [description]

## Common Commands

### Build and Package
```bash
[build command]
```

### Run Tests
```bash
[test command]
```

### [Other Commands]
```bash
[command]
```

## Configuration Notes

- [Important configuration notes]
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
ドキュメント言語: 日本語

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

### 2. プロジェクト言語の尊重

- **重要**: 3つのファイル（product.md、structure.md、tech.md）は、プロジェクトで使用されている主要言語で記述してください
- 日本語プロジェクトなら日本語、中国語プロジェクトなら中国語で記述
- 技術用語やプロジェクト固有の用語は、元の言語のまま記述することで、後日LLMが検索しやすくなります
- 例: 日本語プロジェクトの場合
  - 良い例: `業務管理システム`、`データ計算処理`、`レポート生成機能`
  - 悪い例: `Business Management System`、`Data Calculation Processing`

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
- [ ] **命名規則に複数のパターンがある場合、それぞれの用途を明確に区別している**
- [ ] front-matterが含まれている

### structure.md
- [ ] ディレクトリ構造が視覚的に表現されている
- [ ] パッケージ命名規則が説明されている
- [ ] 主要なアーキテクチャパターンが記載されている
- [ ] テストコードの配置が説明されている
- [ ] **ファイル命名規則とクラス命名規則の対応関係が明確に記載されている**
- [ ] front-matterが含まれている

### tech.md
- [ ] ビルドシステムとバージョンが記載されている
- [ ] 主要フレームワーク・ライブラリがバージョン付きで列挙されている
- [ ] データベース情報が含まれている
- [ ] よく使うコマンドが記載されている
- [ ] テストフレームワークが説明されている
- [ ] front-matterが含まれている

---

## 命名規則の検証方法
### 1. 検証用チェックリスト

Steering Rules作成後、以下を確認してください：

- [ ] 各命名パターンに具体例が3つ以上記載されている
- [ ] 複数パターンがある場合、それぞれの用途が明確に区別されている
- [ ] 実際のプロジェクトファイルと照合し、パターンが一致している
- [ ] クラス名、ファイル名、URL等の対応関係が表形式で示されている
- [ ] 特殊なケース（BaseController等）がある場合、その説明が含まれている

---

## トラブルシューティング

### Q: プロジェクト情報が不足している場合は？

A: 以下の順序で情報を収集してください:
1. `pom.xml` または `build.gradle` を確認（技術スタック）
2. `README.md` を確認（プロジェクト概要）
3. ソースコードのパッケージ構造を確認（構造情報）
4. 主要なクラスファイルを確認（アーキテクチャパターン）
5. **実際のファイル名とクラス名を複数サンプリングして命名パターンを確認**

### Q: 複数のサブプロジェクトがある場合は？

A: 各サブプロジェクトに個別の `.kiro/steering/` を作成するか、
共通部分をルートに配置し、サブプロジェクト固有の情報を各ディレクトリに配置します。

### Q: 命名規則に複数のパターンがある場合は？

A: 以下を必ず明記してください:
- **各パターンの名称**（例: プログラムID、画面ID、モジュールID）
- **各パターンの用途**（例: クラス名用、URL用、ファイル名用）
- **具体的な例を3つ以上**
- **パターン間の対応関係を表形式で記載**
- **実際のプロジェクトファイルで検証**

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
