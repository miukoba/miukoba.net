---
date: 2013-12-14
title: PHP日本語版のDash用Docsetを作った (user notes付き)
slug: Japanese-PHP-Docset-for-Dash
---

## Dash でPHPマニュアル日本語版！

こんな感じ

![image](https://www.evernote.com/shard/s29/sh/0b11e0aa-8461-42b6-bdf5-9b95ae32d134/6cdb6656ae9caa4ac6c1bb4f3e428c12/deep/0/スクリーンショット-2013-12-14-10-06.png)

#### ダウンロードはこちら

[miukoba/phpdoc-ja-docset](https://github.com/miukoba/phpdoc-ja-docset)


<!--more-->

## 流れ

* 普段会社で PHP を書いている
* Dash は便利なのだが、やっぱり日本語のヘルプファイルが欲しくなる
  * [Dash - Documentation Browser, Snippet Manager - Kapeli](http://kapeli.com/dash)
  * ちなみに API リファレンスの検索ばっかり取り上げられてるような気がするんですが、snippet management もめっちゃ便利です
* Dash Docsets が自分で作れることを知る
  * [Generating Dash Docsets - Kapeli](http://kapeli.com/docsets)
* PHP Document がどこから Download できるかを探す
* user notes 入りが良かったが、 user notes を含むファイルは chm 形式しか無いことを知る
  * [PHP: Download documentation](http://www.php.net/download-docs.php)
* chm を HTML に変換するソフトを探すも mac で良さそうなものを見つけられない
* もっと調べたら、 chm から HTML を抽出する方法の記載を見つける (Wikipediaこんなのまで載ってるとかすげえ)
  * [Microsoft Compiled HTML Help - Wikipedia](http://ja.wikipedia.org/wiki/Microsoft_Compiled_HTML_Help)
* Linux で apt-get する手順だったので、とりあえず vagrant up する
  * ちなみに Vagrant は 1.4
  * getting-started に載ってる precise32 でいいや
  * 
```
mac > mkdir docset-vm
mac > cd docset-vm
mac > vagrant init precise32 http://files.vagrantup.com/precise32.box
mac > vagrant up
mac > vagrant ssh
```
* VM で作業
  * 
```
vagrant@precise32:~$ wget -O php_enhanced_ja.chm http://jp2.php.net/get/php_enhanced_ja.chm/from/this/mirror
vagrant@precise32:~$ sudo apt-get install libchm-bin
vagrant@precise32:~$ extract_chmLib php_enhanced_ja.chm php_enhanced_ja
```
* mac にファイルを移動 
  * /vagrant ディレクトリは、デフォルトで host (mac) と共有されている
  * 
```
vagrant@precise32:~$ mv php_enhanced_ja /vagrant/
```
* ブラウザで確認（良さそう）
  * file:///path/to/vagrant/vm/php_enhanced_ja/res/index.html
* [Generating Dash Docsets - Kapeli](https://outlook.com/%E2%80%8E) の 7. Any HTML Documentation の通り作業しようかと思ったけどめんどくさすぎる・・・・・
* Dash で Download できる PHP の Docset (英語) と同じ構成なので、そのまま使い回せるのではないかと重い試してみる
* うまくいった！！！！！ 
  * 詳細は後述
* 後片付け
  * chm の解凍に使った VM は要らないので削除
  * 
```
mac:~$ cd /path/to/vagrant/vm
mac:~$ vagrant destroy
```

<!--more-->

## Dash の PHP.docset (en) を利用して (ja) を作成する

#### PHP.docset を コピー (とりあえず Desktop)

Docset は dash の Preferences から開ける

![image](https://www.evernote.com/shard/s29/sh/b6ddca10-f2b3-4ac5-af77-38084eb7486f/97e17fec71bf1848ecda0c7fbbe37d02/deep/0/Docsets-と-php_enhanced_ja.docset.png)

構成はこんな感じ

```
PHP.docset
└── Contents
    ├── Info.plist
    └── Resources
        ├── Documents
        │   ├── なんかすごい色いろある
        ├── LICENSE
        └── docSet.dsidx
```

#### 名前を変更

```
mac > mv PHP.docset php_enhanced_ja.docset
```


#### docSet.dsidx と Documents の中を調べる

docSet.dsidx が、SQLiteのファイル。検索時のインデックスが保存されている

Litaで覗いてみる

* [Lita - SQLite Administration Tool | David Deraedt](http://www.dehats.com/drupal/?q=node/58)
  * Lita 開発止まってたのね・・・

![image](https://www.evernote.com/shard/s29/sh/1a960d4d-de04-4151-a243-3bb59d6e1099/63434a37329b0d3ad1449761edf6c474/deep/0/Lita---SQLite-Database-Administration.png)

Documents のなかにいろいろフォルダがあるけれど www.php.net/manual/en/ しか使用されていないっぽことが判明

Contents/Resources/Documents/www.php.net/manual/en/ の中身を日本語版に置き換えるだけで使える予感

#### chm から作成した html ファイルに置き換える

Documents 以下の www.php.net 以外は要らなそうなので削除

SQLite の書き換えがめんどくさいので、日本語版だけどenという名前はそのままにする

ファイルはこんなかんじになる

```
.
└── Contents
    ├── Info.plist
    └── Resources
        ├── Documents
        │   └── www.php.net
        │       └── manual
        │           └── en
        │               ├── about.formats.html
        │               ├── about.generate.html
        │               ├── about.howtohelp.html
        │               ├── about.html
        │               ├── about.more.html
        │               ├── about.notes.html
        │               ├── about.phpversions.html
        │               ├── about.prototypes.html
        │               ├── about.translations.html
 - - - - - - - - - - -  - - 省略 - - - - - - - - - - - - -
        │               ├── zlib.requirements.html
        │               ├── zlib.resources.html
        │               └── zlib.setup.html
        ├── LICENSE
        └── docSet.dsidx
```

#### Info.plist 書き換える

string のところを変更する


変更前

```
<?xml version="1.0" encoding="UTF-8"?>
<plist version="1.0">
<dict>
<key>CFBundleIdentifier</key>
<string>php</string>
<key>CFBundleName</key>
<string>PHP</string>
<key>DocSetPlatformFamily</key>
<string>php</string><key>dashIndexFilePath</key><string>www.php.net/manual/en/index.html</string>
<key>isDashDocset</key><true/></dict>
</plist>
```


変更後

```
<?xml version="1.0" encoding="UTF-8"?>
<plist version="1.0">
<dict>
<key>CFBundleIdentifier</key>
<string>php-japanese</string>
<key>CFBundleName</key>
<string>PHP-japanese</string>
<key>DocSetPlatformFamily</key>
<string>php</string><key>dashIndexFilePath</key><string>www.php.net/manual/ja/</string>
<key>isDashDocset</key><true/></dict>
</plist>
```

#### dash に追加

完成した php_enhanced_ja.docset を開けば追加される

![image](https://www.evernote.com/shard/s29/sh/a5b76c32-fde6-4e7e-aa5e-85638731bdea/372233125bb848e7c5abc0133d7d4c02/deep/0/Docsets.png)



