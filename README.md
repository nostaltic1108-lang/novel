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

## 🏷️ カテゴリを増やす

1. `articles/` に新しいフォルダを作る（例：`articles/essay/review/`）
2. `index.html` の上部にある `CATEGORY_LABELS` と `SUBCATEGORY_LABELS` に表示名を追加：

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
├── images/           ← 画像置き場
└── README.md         ← このファイル
```
