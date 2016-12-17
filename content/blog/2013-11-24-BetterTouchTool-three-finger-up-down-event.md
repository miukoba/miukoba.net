---
date: 2013-11-24
title: BetterTouchToolで3本指swipe up/down時にスクロールしないように設定する方法
slug: BetterTouchTool-three-finger-up-down-event
---

BetterTouchTool で Trackpad の3本指 swipe up/ swipe down に操作を割り当てると、アプリによっては割り当てた操作だけでなく、スクロールもしてしまって不便。

<!--more-->

自分の場合は、ブラウザや iTerm2 のタブ移動に割り当てており、 iTerm2 の場合はタブ移動したタイミングで少しスクロールしてしまい不便。

スクロールしないようにするためには、設定の `Enable system three finger up / down swipe events` にチェックを入れればいい。

予想だが、デフォルトだとシステムイベントとは別のイベントとしてBTTに設定した操作を実行しており、システムイベントのスクロールが別途実行されてしまっていると思われる。

`requires BTT restart` と書いてあるとおり、設定後は BetterTouchTool の再起動をお忘れなく。

![BTTの設定箇所](https://www.evernote.com/shard/s29/sh/e401a120-6cd7-4195-910e-e716bfbebe7b/297986b67d14c92bb459afab17c1ee2e/deep/0/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88-2013-11-24-0-58.png)
