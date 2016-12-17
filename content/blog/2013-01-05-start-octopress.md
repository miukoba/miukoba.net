---
date: 2013-01-05
title: Octopressはじめました
slug: start-octopress
---

## Octpressについて

[Octopress](http://octopress.org/)を使いはじめました。
Octopress は jekyll を使って作るブログ構築用フレームワークです。
GitHub Pages と組み合わせると、とても簡単かつ無料でブログが作れます。

<!-- more -->

あらかじめ静的ページを生成しておくという意味では、MovableTypeみたいな感じでしょうか。
MovableTypeは使った事無いですが。

Octpressやjekyllについては詳しく説明してくださっているサイトがあるのでリンクだけ貼っておきます。

* [Big Sky :: githubとjekyllとoctopressで作る簡単でモダンなブログ](http://mattn.kaoriya.net/software/lang/ruby/20111017205717.htm)
* [WordPressよりjekyllで本格的ブログを作りたくなる、かもしれないまとめ | ゆっくりと…](http://tokkono.cute.coocan.jp/blog/slow/index.php/programming/making-blog-with-jekyll/)
* [Octopressのインストールから運用管理まで - T.I.D.](http://tokkonopapa.github.com/blog/2011/12/30/octopress-on-github-and-bitbucket/)

## インストール
Octopressのドキュメント [Octopress Setup - Octopress](http://octopress.org/docs/setup/) を見ながら進める。

macbook airで、rvmを使用してruby 1.93 導入済みだったので、事前準備はとくに無くすんなり終わりました。
Windowsだといろいろ詰まるらしい・・・？

## 初期設定（_config.yml）

こちらも公式ドキュメント [Configuring Octopress - Octopress](http://octopress.org/docs/configuring/) を見ながら設定。

変更箇所は以下

```
url: http://miukoba.github.com
title: mimemo
subtitle: miukoba memo
author: miukoba
date_format: "%Y-%m-%d"
email: miukoba@gmail.com
excerpt_link: "つづきを読む"
github_user: miukoba
twitter_user: miua
facebook_like: true
```

## テーマの変更
ここにまとまっています。

* [3rd Party Octopress Themes · imathis/octopress Wiki](https://github.com/imathis/octopress/wiki/3rd-Party-Octopress-Themes)

プレビューをひと通り見てgreyshadeを選びました。

* [shashankmehta/greyshade · GitHub](https://github.com/shashankmehta/greyshade)

ここでも、Readmeのとおり実行しただけ。colorは #2571b8（greyshadeの作者と同じ色）を指定。

```
$ git clone git@github.com:shashankmehta/greyshade.git .themes/greyshade
$ echo "\$greyshade: #2571b8;"
$ rake install['greyshade']
$ rake generate
```

ツイートを表示したくなかったので、_config.ymlを変更。

```
twitter_tweet_count: 0
```

## faviconの変更

好きなpngファイルで、source/favicon.png を置き換え。

## 独自ドメインを設定

このへんを見つつ設定

* [Deploying to Github Pages - Octopress](http://octopress.org/docs/deploying/github/#custom_domains)
* [GitHub PagesでCustom Domainを利用する - Glide Note - グライドノート](http://blog.glidenote.com/blog/2011/12/20/how-to-use-custom-domain-on-github-pages/)


## コメント欄の追加

OctpressはDisqus（コメントシステム）埋め込みに標準で対応しています。

アカウントは持っていたので、Disqusにサイトを追加して、IDをメモ。_config.ymlに記載。

```
disqus_short_name: mimemo
```

## はてなブックマークボタン追加

source/_includes/post/sharing.html に追加。

```
 <div style="float:left">
   <a href="http://b.hatena.ne.jp/entry/{{ site.url }}{{ page.url }}" class="hatena-bookmark-button" data-hatena-bookmark-layout="standard" title="このエントリーをはてなブックマークに追加"><img src="http://b.st-hatena.com/images/entry-button/button-only.gif" alt="このエントリーをはてなブックマークに追加" width="20" height="20" style="border: none;" /></a>
   <script type="text/javascript" src="http://b.st-hatena.com/js/bookmark_button.js" charset="utf-8" async="async"></script>
 </div>
```

## 日々ブログを書くときのコマンド

#### 新規投稿テンプレート作成
ここで指定する文字列はURLに使われるので、英数だけで指定する

```
rake new_post['post title']
```

#### 記事をかく
好きなエディタで作成されたファイルを編集する。あたまの --- から --- は、jekyllのFront-Matter。

[YAML Front Matter · mojombo/jekyll Wiki](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter)

titleを変更する。記事タイトルに日本語を使いたい場合はこの時点で変更する。
categories はスペース区切りで複数指定可能。

source/_posts/yyyy-MM-dd-post-title.markdown

#### 静的ページの生成
```
rake generate
```

#### 記事の確認
```
rake preview
```
を実行後に、ブラウザで http://localhost:4000/ にアクセス。


#### デプロイ

コマンド一発！

```
rake deploy
```

#### ソースもpush

```
git add .
git commit -m 'comment'
git push origin source
```

## その他

#### エディタ

markdownエディタとしてMouを使ってます。リアルタイムプレビューが便利で見た目もキレイ。

[Mou - Markdown editor for web developers, on Mac OS X](http://mouapp.com/)


こんなかんじ。

![image](https://www.evernote.com/shard/s29/sh/0d268d45-b3a0-49f0-babd-c9367a5530d6/d0ce0ae5fe8e6c5226b227e37c8160ad/deep/0/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202013/01/05%2022:22.jpg)

#### つづきを読む
 
```
 <!-- more -->
```
を書くと、一覧ページでは省略され、続きを読むリンクが表示されます。

リンク文字列は、_config.yml の excerpt_link で変更可能。

## まとめ
というわけで環境が整いましたので、頑張ってブログ書きます。

---

**※2013/04/21追記**

サイドバーを色々弄りたくなったので、今はデフォルトテーマの色を変えただけに戻しています。



