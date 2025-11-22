# ToYama's blog

ToYamaの個人ブログサイトです。[Hugo](https://gohugo.io/)と[hugo-theme-stack](https://github.com/CaiJimmy/hugo-theme-stack/)テーマを使用して構築されています。

## プロジェクトの概要

このプロジェクトは、Hugo静的サイトジェネレーターを使用した個人ブログサイトです。

### 主な特徴

- **静的サイト生成**: Hugoを使用して高速で安全なWebサイトを生成
- **テーマ**: hugo-theme-stackテーマを採用
- **多言語対応**: 日本語・英語のコンテンツをサポート
- **自動デプロイ**: GitHub Actionsを使用してGitHub Pagesに自動デプロイ
- **コンテナ化**: Docker Composeによる簡単なローカル開発環境

### 技術スタック

- [Hugo](https://gohugo.io/) v0.134.3 (Extended版)
- [hugo-theme-stack](https://github.com/CaiJimmy/hugo-theme-stack/) テーマ
- Docker & Docker Compose
- GitHub Actions (CI/CD)
- GitHub Pages (ホスティング)

## 環境構築の仕方

### 前提条件

以下のいずれかの方法で環境構築が可能です：

#### 方法1: Docker を使用する場合（推奨）

- [Docker](https://www.docker.com/get-started) がインストールされていること
- [Docker Compose](https://docs.docker.com/compose/install/) がインストールされていること

#### 方法2: ローカルにHugoをインストールする場合

- [Hugo Extended版](https://gohugo.io/installation/) v0.134.3 以上
- [Git](https://git-scm.com/) 
- [Dart Sass](https://sass-lang.com/dart-sass)

### セットアップ手順

#### 1. リポジトリのクローン

```bash
git clone --recursive https://github.com/ToYama170402/ToYama170402.github.io.git
cd ToYama170402.github.io
```

**注意**: `--recursive` オプションは、テーマをサブモジュールとして取得するために必要です。

もしクローン時に `--recursive` を忘れた場合は、以下のコマンドを実行してください：

```bash
git submodule update --init --recursive
```

#### 2. ローカル開発サーバーの起動

##### 方法A: Docker Compose を使用（推奨）

```bash
docker-compose up
```

ブラウザで http://localhost:1313 にアクセスしてサイトを確認できます。

ファイルの変更は自動的に反映されます（ホットリロード）。

##### 方法B: ローカルのHugoを使用

```bash
cd src
hugo server -D
```

ブラウザで http://localhost:1313 にアクセスしてサイトを確認できます。

### 3. コンテンツの追加

新しい記事を作成する場合：

```bash
# Docker Composeを使用する場合
docker-compose exec hugo hugo new content/post/YYYY-MM-DD.md

# ローカルのHugoを使用する場合
cd src
hugo new content/post/YYYY-MM-DD.md
```

作成されたMarkdownファイルを編集して記事を書きます。

## プロジェクト構造

```
.
├── .github/
│   └── workflows/
│       └── hugo.yml          # GitHub Actions設定（自動デプロイ）
├── src/                      # Hugoプロジェクトのルート
│   ├── archetypes/           # コンテンツのテンプレート
│   ├── content/              # ブログ記事などのコンテンツ
│   │   └── post/            # ブログ記事
│   ├── themes/               # Hugoテーマ
│   │   └── hugo-theme-stack/ # 使用中のテーマ（サブモジュール）
│   ├── assets/               # アセットファイル
│   ├── static/               # 静的ファイル
│   └── hugo.yaml             # Hugo設定ファイル
├── docker-compose.yml        # Docker Compose設定
└── README.md                 # このファイル
```

## デプロイ

このサイトはGitHub Actionsを使用して自動的にデプロイされます。

- `main`ブランチへのプッシュ時に自動的にビルド・デプロイされます
- 毎日午前4時（UTC）に定期ビルドが実行されます
- デプロイ先: https://toyama.github.io

## ライセンス

Copyright © 2020 ToYama

## リンク

- ブログサイト: https://toyama.github.io
- Twitter: [@ToYamaSoujin](https://twitter.com/ToYamaSoujin)
- YouTube: [@ToYamaSoujin](https://www.youtube.com/@ToYamaSoujin)
- GitHub: [@ToYama170402](https://github.com/ToYama170402)
