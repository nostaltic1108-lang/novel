# My Writing Room

小説やブログを公開するための静的サイトです。  
GitHub Pagesで無料ホスティングでき、**ビルドツール不要**で動きます。

## 🚀 セットアップ（5分）

1. このフォルダをGitHubリポジトリにアップロード
2. リポジトリの **Settings → Pages → Source** で `main` ブランチを選択
3. 数分待つと `https://あなたのユーザー名.github.io/リポジトリ名/` で公開されます

## ✏️ 記事を追加する方法

### ステップ1：記事ファイルを作る

`articles/` の中に `.md`（Markdown）ファイルを置きます。  
テキストエディタ（メモ帳でもOK）で書けます。

```
articles/
├── novel/          ← 大カテゴリ
│   ├── fantasy/    ← 小カテゴリ
│   │   └── my-story.md
│   └── sf/
└── blog/
    ├── daily/
    └── tech/
```

### ステップ2：articles.json に追加する

`articles.json` を開いて、新しい記事の情報を追加します：

```json
{
  "title": "記事のタイトル",
  "file": "articles/novel/fantasy/my-story.md",
  "category": "novel",
  "subcategory": "fantasy",
  "date": "2026-04-01",
  "excerpt": "一覧に表示される要約文"
}
```

### ステップ3：GitHubにプッシュ（またはブラウザからアップロード）

これだけで記事が公開されます！

## 🖼️ 画像を使う

1. `images/` フォルダに画像ファイルを入れる
2. 記事の中に `![説明文](images/ファイル名.jpg)` と書く

## 🔗 リンクカードを貼る

記事の中に以下のように書くと、URLがカード形式で表示されます：

````
```linkcard
url: https://example.com
title: サイトのタイトル
description: サイトの説明文
image: https://example.com/ogp-image.jpg
```
````

- `url` と `title` は必須、`description` と `image` は省略OK
- `image` にはリンク先のOGP画像URLなどを指定します

## 🏷️ カテゴリを増やす

1. `articles/` に新しいフォルダを作る（例：`articles/essay/review/`）
2. `index.html` の上部にある `CATEGORY_LABELS` と `SUBCATEGORY_LABELS` に表示名を追加：

## 📄 一覧に載せないページを作る（About等）

`articles.json` に `"hidden": true` を付けると、一覧・トップに表示されなくなります。
URLで直接アクセスするか、ヘッダーにリンクを置いて使います。

### ステップ1：Markdownファイルを作る

`pages/` フォルダなどに `.md` ファイルを置きます（場所は自由）。

### ステップ2：articles.json に追加する

```json
{
  "title": "About",
  "file": "pages/about.md",
  "hidden": true
}
```

`category`、`subcategory`、`date`、`excerpt` は省略OKです。

### ステップ3：ヘッダーにリンクを追加する（任意）

`index.html` の `HEADER_PAGES` にリンクを追加できます：

```javascript
const HEADER_PAGES = [
  { label: 'About', file: 'pages/about.md' },
  { label: 'お問い合わせ', file: 'pages/contact.md' },
];
```

```javascript
const CATEGORY_LABELS = {
  'novel':  '小説',
  'blog':   'ブログ',
  'essay':  'エッセイ',   // ← 追加
};

const SUBCATEGORY_LABELS = {
  'fantasy': 'ファンタジー',
  'review':  '感想・レビュー',  // ← 追加
};
```

## 🎨 サイト名を変える

`index.html` の中の `SITE_NAME` を書き換えるだけです：

```javascript
const SITE_NAME = 'あなたのサイト名';
```

## 📁 ファイル構成

```
├── index.html        ← サイト本体（これ1つで動く）
├── articles.json     ← 記事の一覧（ここに追記する）
├── articles/         ← 記事ファイル置き場
│   ├── novel/
│   │   ├── fantasy/
│   │   └── sf/
│   └── blog/
│       ├── daily/
│       └── tech/
├── pages/            ← 固定ページ置き場（About等）
├── images/           ← 画像置き場
└── README.md         ← このファイル
```
