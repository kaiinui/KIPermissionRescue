KIPermissionRescue
==================

[iOS] Provide users a guide to give the missing permission.

Designdoc
===

Problem
---

1. iOS, パーミッションの数だけパーミッションを聞くのでうざい
2. iOS, パーミッションの聞き方が無骨なプロンプトなのもあり、「なんのために承認する必要あるのか」分かりにくい
3. パーミッションを拒否されると、そこからのリカバーが困難
  * それぞれのパーミッションの可否を知るコードが統一されていない
  * パーミッションが複数あれば、どんなバリエーションで拒否されているのか、それぞれについてコードを考えなければいけないのが辛い
  * iOS, アプリ内から「設定」へのリンクが置けない。また、コードで再許可のお願いも出来ない。
  * それぞれのパーミッションについて、「再許可」を求めるインストラクションを View として用意するのが辛い

How to solve it
---

1. OS の Permission Prompt の前に、「何故必要か」を書いた View を挟む
2. もし必要不可欠なパーミッションが拒否されていれば、再許可するためのインストラクションをオーバーレイする
  * トーストでの表示も OK
3. 出来るだけパーミッションを求めることを遅延させることを意識する感じに書けるようにする。

ついでに Permission に関連する開発のために

1. Permission を初期化するためのインストラクションを提供する

References
---

- The Right Way to Ask Users for iOS Permissions https://medium.com/@mulligan/the-right-way-to-ask-users-for-ios-permissions-96fa4eb54f2c
- Facebook Messanger App [iOS]
