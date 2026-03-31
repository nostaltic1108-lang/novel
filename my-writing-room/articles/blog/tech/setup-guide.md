# GitHub Pagesでサイトを作った話

このサイトの仕組みをメモしておきます。プログラミングの知識がなくても記事を書けます。

## 記事の追加方法

やることは2つだけです。

**ステップ1：** Markdownファイルを作る

`articles/` フォルダの中に `.md` ファイルを置きます。フォルダ構成はこんな感じ：

```
articles/
├── novel/
│   ├── fantasy/
│   │   └── my-story.md    ← ここに記事ファイル
│   └── sf/
│       └── another.md
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

1. `images/` フォルダに画像ファイルを置く
2. 記事の中で `![説明](images/ファイル名.jpg)` と書く

## Markdownの書き方

よく使うものだけ覚えれば十分です。

- `# 大見出し` → 大見出し
- `## 中見出し` → 中見出し
- `**太字**` → **太字**
- `---` → 区切り線
- `> 引用文` → 引用ブロック

詳しくは「Markdown 書き方」で検索してみてください。
