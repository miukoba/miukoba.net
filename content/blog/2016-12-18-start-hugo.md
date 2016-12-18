---
date: 2016-12-18
title: Octopressからhugoに乗り換えた
slug: start-hugo
---

## 理由

なんとなく。

- blog書こうかなと思ったけど、Octopressで作ったブログを放置しすぎて使い方を忘れていた
- Octopressからhugoに乗り換えた見たいな話を何度か見かけた
- どうせ1からなので新しいのを試してみようと思った

<!--more-->


## URLを維持する

- permalinksとslugを使用して、Octopressのときと同じURL構造に設定
  - 公式ドキュメント: [Hugo - Permalinks](https://gohugo.io/extras/permalinks/)

config.toml

```
[permalinks]
blog = "/blog/:year/:month/:day/:slug/"
```

各ページのmarkdownファイル、ヘッダー部分

```
slug: unix-philosophy
```

-> http://www.miukoba.net/blog/2014/01/14/unix-philosophy/


## CircleCIを使用した自動デプロイ設定

[Hugo で作ったサイトを CircleCI で GitHub Pages に自動デプロイ | Born Too Late](https://blog.yuyat.jp/post/auto-deploy-hugo-to-github-pages-with-circleci/)

ほぼこのままで、パッケージだけ最新の0.17に変更しました。感謝！


## コード

[miukoba/miukoba.net](https://github.com/miukoba/miukoba.net) です

