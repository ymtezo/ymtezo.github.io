# Hiroaki Yamato Portfolio & Blog

## ブログ記事の追加方法

### 1. 新しい記事を作成する

`posts/` ディレクトリ内に新しいフォルダを作成し、その中に `index.qmd` ファイルを作成します。

```
posts/
  └── my-new-post/
      └── index.qmd
```

### 2. フロントマター(YAML)を設定する

`index.qmd` の先頭に以下のような設定を追加します:

```yaml
---
title: "記事のタイトル"
description: "記事の説明文"
author: "Hiroaki Yamato"
date: "2025-01-21"
categories: [起業, 地域創生]
image: "画像のURL"
draft: false  # 下書きの場合は true
---
```

### 3. タグ(カテゴリ)について

現在利用可能なタグ:
- `起業`: 起業・スタートアップ関連
- `地域創生`: 地域創生・地方活性化関連

#### 新しいタグを追加する方法

1. `tag-新しいタグ名.qmd` ファイルをルートディレクトリに作成
2. 以下のテンプレートを使用:

```yaml
---
title: "#新しいタグ"
listing:
  contents: posts
  sort: "date desc"
  type: default
  categories: true
  filter-ui: false
  include:
    categories: "新しいタグ"
  fields: [image, date, title, description]
page-layout: full
title-block-banner: true
---

新しいタグに関する記事一覧です。
```

3. `index.qmd` にタグボタンを追加:

```html
<a href="tag-新しいタグ名.html" class="btn btn-primary" style="margin: 0.3rem; font-size: 1.1rem; text-decoration: none;">#新しいタグ</a>
```

### 4. サイトをビルドする

```powershell
quarto render
```

または VS Code の Quarto プレビュー機能を使用してください。

## ディレクトリ構造

```
├── posts/              # ブログ記事
│   ├── _metadata.yml   # 記事の共通設定
│   └── [記事名]/
│       └── index.qmd
├── blog.qmd           # ブログ一覧ページ
├── tag-*.qmd          # 各タグのページ
├── index.qmd          # トップページ
└── _quarto.yml        # サイト全体の設定
```
