---
date: 2014-01-14
title: UNIXという考え方―その設計思想と哲学 を読みました
slug: unix-philosophy
---

## 読んだ本

これ

<div class="aalglink-box" style="text-align:left;font-size:small;/zoom: 1;overflow: hidden;">
<div class="aalglink-image" style="float:left;margin:0 15px 10px 0;">
<a href="http://www.amazon.co.jp/o/ASIN/4274064069/miumiua-22/" target="_blank"><img src="http://ecx.images-amazon.com/images/I/518ME653H3L._SL160_.jpg" style="border: none;"></a>
</div>
<div class="aalglink-info" style="line-height:120%;/zoom: 1;overflow: hidden;">
<div class="aalglink-title" style="margin-bottom:10px;line-height:120%;font-size: large;">
<a href="http://www.amazon.co.jp/o/ASIN/4274064069/miumiua-22/" rel="nofollow" target="_blank" style="line-height: 150%;">UNIXという考え方―その設計思想と哲学</a>
</div>
<div class="aalglink-detail" style="margin-bottom:5px;">
Mike Gancarz オーム社
<br>単行本
</div>
<div class="aalglink-detail" style="margin-bottom:5px;">
発売日 : 2001-02
<br>
売り上げランキング : 15590
</div>
<div class="aalglink-link" style="margin-top:10px;">
<a href="http://www.amazon.co.jp/o/ASIN/4274064069/miumiua-22/" rel="nofollow" target="_blank"><img style="border: none;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKQAAAAaCAMAAAAOqwd2AAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAwBQTFRFUUMeUUUj6M2ChHNFZFcx7sddz7Zyw6VUIiIY275yg3A90rt8g2418MVOnItZpYo+uqNkrppjjHUyuKBb0bh0dWY817RUaFYke2o9uqVquJ5VinU9xKxqeWUsn4pNnotTe2k28dSGaVsz3LZMn4Q96t/CtaNy8s5sxqlbPDQbERINaVktSUAi2bZW479a7Mx0kn5F9Mxe3cydlINUPDEUuJxNrJJL069LrJRSlIFL79aS5cVuspVDvp1E7stoFhcQY1MmmH87bWRG8dF8t5lGLCgVY1EimodS8dOBMi0XQz0l2sB527xoIB0PindEVkoqxadYVUgkUUYoaFgoDA4KQDQUJR0Hc2AsQDce6cJZIRsIJR8MwqJOBwoIAAAA/ual9shK/+eo/+ir9cdH/uWh/uSe9slO98xW981a/eKZ9spR/eGV/N+Q+M9f+dJo+NBj/N6M+9qC+tVy+dRt+9yHBAcH+tl9+td4qJNbY1Qsp41KoY1XY1Uup49OpotDn4dGzbBhpo1GzKxUoIxUzK1Yza5c0LFdzrJpzbJly6lMIhwMp5BR5sp/8NB427pjp5FU2bVS0bVr0LJjn4ZD2rdazqxOy6pQ8M5z8taKZFc15cd20bdvJiAQz65V89iPtJxY275t7cZb/eWl28SE5sh3zqxR571Jl34579B3rphftJpUz7BZoIpQyqhI2Ltv3cN9Y1QpmYRK5cNo0LRn1rFN2Ldd9MdLwJ4+s5dJ3cBv3MB1ZFct3cJ648d69MtZrpE+BQgHtZ5fh3pSlolh8cRH6cBRWFI78sdQ2rle+eGi3cWC++SmtZU7tZ9jzrRu+d6TwKFOw6NMx7B0z7l8VUcdc18qXk8haF0718B/yKtZyKtfRj0f07huoI5bs6BroJFnqJZirZZYqY0/8chYf2or88td2sF88cRIOTYlzq5XNjAYYFMq9sxa+92L7sdf9c5iw6JIZl5DUEMc8tua2bpn3b1lVk406tSVwalnYFQvkXo5kns/2MGDwadf4r1W////cI+6EQAAAQB0Uk5T////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////AFP3ByUAAAUZSURBVFjDzZgHUBRXHMYXOSEe6Il0KfGwngQkiBVFFEENInoongd+aXY47vbK7gFRrKCroIKoKJaosccaTe+9N9Jj+qSYhCSmF6P/t8ftHYlx4kxmcr+Ze+/7f//3dr95zC4zy13oHfR2sQ8zOaj3BS71yPCnb/Jhnh1+JJUL3HWjj7MrkCu+3ucp5opnefH9+2Oe+O7Rn2f5FhRytoc+oxyM/n1m+xQUcr7CH1Mp4UyWcrjHnL/71d3z/18oZInCGIfjqjdffIRSvucxS5rRXHLFBAUFPbM9ZHvJwCAqQqL/3abtr1zap5ClCl1++vyD0tIOFPKMxwyAAZ+WXikAmjZLA48ihApd01FmEO52mC683fKmM5tLSzeHIPqSF6OQFm++zo0eyEJ6nHFwwmmxaAPWrHE6tdrnnQFk5jqdsTQFMHItFurksjJX63SuYZu6VjL0uiZUhmmb4I8wHND7+4P1tAc6WMKj9WFed9WGI6+DpTKv8j7LpaCQdg/3v+F6chxdPF5+83gk2O0vIJ9OIooNnewPw5CAfLtdPp0E+y8w5GMclYZmoJlt6rqMCFfpoVJ1jYWkU9mxVbVsGag1XgK2xkp6ezu2+tMw7B4mY3X+49s3KSSv8C5FnKpvopBXK94WRPH54PkaGLZkFWEtv5Z+BgPPT0INX1NTEyWXWXwUtvCUn08gm6DwKp5fD6Y76aTQLKxXHT5MZZZeWq+XOvHe7PHf4xLhH7I9Ouiz2vUppKBwncORd7cwgIVUvB1YLUzCSmElzUICBFms3iEIx8kUhPSiov37cZytOy8gQRBWy7YQHx8fGi8f9EmhVorHUPhJOh1tVyNUqPWTdtKa0FtcpJyUoGab1EgRdkp+taHwqxW8oJCimwEPORxRojiRQg5TzBj8IB7EQnEx/cREiC6RvrAHsFhkzkGXwwYkiuJC2RYpXXl6/VDU12+qZ1HToE4rL4eYAjV1041Suih2L3eRIm6qOk+umnqb/DCROvCbKHqgkFY3P1K6cKtVTdOvilmEiooYTLGuQIXVmgirLCpQFBODFVZrIBJdjjywooLZ1hNVRHX1YFRX11mrfsfkOlQfq6qCtfsx+ap14Ppa23OCQzBNwYNZUW001nlaFNLmpi+9y/vH9GBv85lvtXmnXK8OZCzHEputADYbiQwUZNiWYLktYxpOyY5rQIFNtm22Q+DS2nZm2rhMcA04lNnQAOVeg8Bl2LzIaDBisFf9lBGDlIJClincKz/ZM69xOEZ90WYtwiIa4/DSUiYKUFZGQtajsZS6o9kidCsru4tKFLANS8nZhm29wCa53QvB0xGclpkJz71+M27wFBuCjcj0qpllPKdoCmlWaP2STnHCoG+mZCe5rRZE0KjBvo3QmM2RMJtJRCCyY0QhNMnAPo1mhDmuMLk1stBsRiRbupE23MbOkE2kkzAWyUk4l5OTBs+9zMle+jWkvWz+C62tiqSQJplre3Sk8dakGXIxI/GdbLlGIasj0LIKGpMpEiYTE3FA4Yhphavkv2ek6c8WqleZTCRNGpAwrctZ19iLTfK1G2lbzjqTaayr/DuNjabLQSHnufg2e/TH89x8NeKjsw/M+2fuuP3y9X8LhZzbxpAJowoe7Eni8ZFx2WdHTp/rM1DIBW46d8uj/zj96RnP6/Zkz84LfAYKOcdD5+fiWs69/smdp+f4FMVc4OkbfJzTgVzqkL2P3ezDfLZ3SCpHHwf6+fLHgX70ceAivqKn8iIcig0AAAAASUVORK5CYII=" alt=""/></a>
</div>
</div>
<div class="booklink-footer" style="clear: left"></div>
</div>

<!--more-->

UNIXの使い方ではなく、UNIXの思想・哲学・考え方について書かれている。

2001 発売と結構古い本だけれど、UNIXの思想は今も変わってないのだろう。

## 特に印象に残っているところ

#### スモール・イズ・ビューティフル 、1つのプログラムには1つのことをうまくやらせる

* 1つの巨大なプログラムにしようとする誘惑に負けずに、シンプルさを追求する。
* 小さいのでわかりやすく、保守しやすい。小さなプログラムは他のツールと組み合わせやすい。
* しのびよる多機能主義（creeping featurism）の犠牲にならないようにする。
* 現在の（1つの）仕事に集中することによって、野郎としていることの本質をつかめる。1つのことをうまくやるように作れないのであれば、おそらく問題をまだ完全には理解していない。

#### 人間による3つのシステム

* 第1のシステム
  * 無駄がなくて俊敏な計算機
  * 多機能性・柔軟性に欠
* 第2のシステム
  * 第1のシステムの成功に魅かれ、えせ専門家が集まってきて作成される
  * ぜい肉がつき、遅い
  * 機能は多くなるが、性能が犠牲になる
* 第3のシステム
  * 第1、第2の間の最良の特徴を組み合わせる
  * 意欲と才能を持った誠実な専門家がシステムのさまざまな側面を強化する
  * 本当に必要な機能だけが残され、適正なリソースで多くのことができるようになる
  * 第3のシステムこそが最大の利便性をもたらすシステムである

第3のシステムを作るには、他の2つのシステムを作るしか無い、UNIX開発者は、大きな仕様書の作成は後回しにして、はやくからプロトタイプを作成しフィードバックを繰り返しながら3に進んでいくから3への到達が早い。

このへんはGitHubとかの登場もあって、OSSに関してはサイクルがどんどん早くなっているような気がする。


#### 効率性より移植性

Atari の事例が乗っていて面白かった。

最高の効率を誇るソフトウェアが、新しいハードウェアが発表された日をもってその価値が大暴落した。
移植性が全くなかったから。

[アタリショック - Wikipedia](http://ja.wikipedia.org/wiki/%E3%82%A2%E3%82%BF%E3%83%AA%E3%82%B7%E3%83%A7%E3%83%83%E3%82%AF)

	良いプログラムは死なず、ただ新しいハードウェアに移植されるのみ


#### 数値データはASCIIフラットファイルに保存する

* 扱いやすい
* UNIX の様々なツール（diff, grep, sed などたくさん）を組み合わせることができる

最近は自然と、後でパースすることを考えますね。


#### 全てのプログラムはフィルタにする

	プログラムはデータを作らない。人間がつくる　

これが結構衝撃だった。自分もデータはアプリケーションが作ることもあると思っていた。

でも、Photoshop みたいな画像編集アプリケーションだってマウスやタブレットを動かした結果データだし、ワードプトセッサだって人間がキーボードが打った結果だし、Webサイトのアクセスログだって人間がサイトにアクセスした時に生成されるもので、どんなブラウザでどのサイトにいつアクセスしたのかも、すべて人間がデータを作っていることにつながる。
コンピュータはあくまでデータを別の形式へ変換しているだけ。

UNIX でいうとstdin、stdout、stderr をちゃんと使おう、という話が載っているのだけれど、これはもっと上位のレベルでいろいろと考えさせられる。
これを考えるとすぐ何かに活かせるかというとちょっと分からないが、データは人間が作っているということを覚えておきたい。



## 全体の感想

多くの考え方に共感した。

小さくシンプルに作って組み合わせることや、はやめのプロトタイプは最近意識している。

フィルタとして振る舞うように、というのはあまり考えもしなかったので、特に意識してみたいと思う。

ただやっぱりUNIXのコマンドはとっつきにくい。
長時間かかわる開発者向けのインタフェースとしてはいいけれど、ちょっとだけ使われるようなインタフェース（APIとか）や、非開発者へのインタフェース（WebサイトのGUI）とかはまた違う考え方・優先度になると思うので、相手をよく考えて作りたいとも思った。


## 買う前に

150ページの薄い本だがはじめの40ページ位がプレビューで読める。こんなに読めるのか・・・

後5ページくらい読めたら3章が終わるのに。いいところで切るものだ。

[UNIXという考え方: その設計思想と哲学 - Mike Gancarz - Google ブックス](http://books.google.co.jp/books?id=5XzfIACY0G8C&printsec=frontcover&dq=isbn:4274064069&hl=ja)




