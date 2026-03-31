# GitHub Pagesでサイトを作った話

このサイトの仕組みをメモしておきます。プログラミングの知識がなくても記事を書けます。

## 記事の追加方法

やることは2つだけです。

**ステップ1：** Markdownファイルを作る

`articles/` フォルダの中に `.md` ファイルを置きます。フォルダ構成はこんな感じ：

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

**ステップ2：** `articles.json` に1行追加する

```json
{
  "title": "記事のタイトル",
  "file": "articles/novel/fantasy/my-story.md",
  "category": "novel",
  "subcategory": "fantasy",
  "date": "2026-04-01",
  "excerpt": "記事の要約を一文で"
}
```

これだけで新しい記事が公開されます。

## 画像を入れるには

1. `images/` フォルダに画像ファイルを入れる
2. 記事の中で `![説明](images/ファイル名.jpg)` と書く

## リンクカードを貼るには

URLをカード形式で表示できます。記事の中に次のように書くだけです：

````
```linkcard
url: https://example.com
title: サイトのタイトル
description: サイトの説明文をここに書きます
image: https://example.com/ogp-image.jpg
```
````

`title` と `url` だけでもOKです。`description` と `image` は省略できます。

実際の表示はこんな感じ：

```linkcard
url: https://docs.github.com/ja/pages
title: GitHub Pages のドキュメント
description: GitHub Pages を使って、GitHub のリポジトリから直接ウェブサイトをホストできます。
image: https://github.githubassets.com/assets/github-logo-55c5b2ea39ec.png
```

```linkcard
url: https://www.markdownguide.org
title: Markdown Guide
description: Markdownの基本的な書き方をまとめたガイドサイトです。
image: https://www.markdownguide.org/assets/images/markdown-guide-og.jpg
```

## Markdownの書き方

よく使うものだけ覚えれば十分です。

- `# 大見出し` → 大見出し
- `## 中見出し` → 中見出し
- `**太字**` → **太字**
- `---` → 区切り線
- `> 引用文` → 引用ブロック
