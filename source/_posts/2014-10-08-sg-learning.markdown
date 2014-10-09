---
layout: post
title: "SonicGardenコードレビュー勉強会#2 に参加しました"
date: 2014-10-08 12:03:37 +0900
comments: true
categories: Ruby,Rails,SonicGarden
---
広島からリモートで、SonicGardenコードレビュー勉強会#2 に参加しました。

![sonic_garden](http://www.sonicgarden.jp/assets/logo-535075f3e242d36af1a349451b6bdabf.png)

<!-- more -->

# 何をしたか
[SonicGarden](http://www.sonicgarden.jp/)さんの主催する、コードレビュー勉強会に参加しました。

Ruby on Railsのソースコードレビューになります。

今回で２回目です。10名の参加でした。

# なぜ参加したのか
実は、私はSonicGardenさんの[ソニックガーデンギルド](http://www.sonicgarden.jp/guild)に挑戦中なのです。

その一環としてコードレビューを受けるのですが、ほかの人のコードレビューにも参加して、学習を加速させるというわけです。

# どうやったのか
[Google Hangouts on Air](http://www.google.com/intl/ja/+/learnmore/hangouts/onair.html)というサービスを利用して参加しました。

これは、ライブ配信を行いながらビデオ通話やチャットができ、配信を終了するとYoutubeに動画として登録される、というものです。すごい！

レビューアはCTOの松村さんです。

# 困ったこと
はじめのうち、音声がハウリングしてしまい、よく聞き取れなくなりました。

レビューアとレビューイ以外がマイクをOFFにするといい具合になったので、チャット等で質問を投げる形式ですすめました。

# 感想
コードレビューをリアルタイムで視聴して、その場で質問できるというのは、すごくよい勉強になると思いました。

今回は見ながら考えてばかりで、質問投げれなかったのですが…

# 学んだこと
今回も含め、過去のレビュー動画を見て学んだことを、列挙してみます。

###全般
- 極力コードが短くなるようにする
- ひとつのメソッドにひとつの仕事を書く
- セッションに大きなデータ入れない
- Ruby1.9以降のhashシンタックスを使ってコードを短く書く

###controller
- ロジックはconrollerではなくmodelに書く
- scaffoldくらいの量のcontrollerで機能を実現できるのが理想
- 表示に関する処理は、controllerではなくviewやhelperに書く
- 共通した処理はbefore_actionなどのフィルターにまとめる
- find!メソッドでデータ取れなければ、例外で404ページに飛ばせる

###model
- 正しいリレーションにする （belongs_toを書く） 
- scopeでModelに検索条件を定義できる
- ["sexy" validations](https://github.com/satour/rails-style-guide/blob/master/README-jaJA.md#sexy-validations) を利用する
- ActiveRecordのメソッドチェインを使って流れるように書く
- after_saveなど、ActiveRecordのコールバックを効果的に使う
- アソシエーションしたモデルは、直接操作しない
- 親オブジェクトからメソッドチェイン的にbuildを呼び出すと、引数忘れがない
- find_or_create_by便利
- 1対多のモデルで[accepts_nested_attributes_for](http://blog.livedoor.jp/sasata299/archives/51931176.html)を使うとコードがすっきりする
- has_manyなモデルはviewで[fields_for](http://railsdoc.com/references/fields_for)を使う
- [default_value_for](https://github.com/FooBarWidget/default_value_for)を使うと、modelにデフォルト値が簡単に書ける

###view
- helperを使ってDRYにする
- erbで文字列に変数を連結するときは、+でつなげるより、#{ 変数 } を使う
- [simple_form](https://github.com/plataformatec/simple_form)を使うと、シンプルなフォームなら早く作れる（デザインが凝った画面は大変かも）
- パンくずリストは[gretel](https://github.com/lassebunk/gretel)を使うとよい
- hamlでインデントつけてもHTML通りにならない。[content_tag_for](http://railsdoc.com/references/content_tag_for)を使う(これは好み)

###routes
- routesのresourcesブロックでmember（単票系）やcollection（一覧系）が使える
- リソースを入れ子にして、親を only:[ ] だけにすると、子供のURLのみ生成
- モデルのカーディナリティを意識したURL設計をする

###そのほか
- githubでURLをcompare/<ハッシュ>...masterと打てばコンペアできる
- [devise](https://github.com/plataformatec/devise)と[omniauth](https://github.com/intridea/omniauth)で、Twitterとgithubアカウントでのログインを可能に
- [better_errors](https://github.com/charliesome/better_errors)、[binding_of_caller](https://github.com/banister/binding_of_caller)を入れて、エラー画面でreplできる
- [hashie](https://github.com/intridea/hashie)を使って、ハッシュにドットでアクセスできる
- [enumerize](https://github.com/brainspec/enumerize)を使うと列挙が扱える

# まとめ
とても勉強になります！また参加したいです。

ちなみにSonicGardenさんでは[ギルド参加者を募集しています](http://www.sonicgarden.jp/guild)。

[納品のない受託開発](http://www.sonicgarden.jp/category/concept/)に興味のあるエンジニアは、申し込んでみるとよいのではないでしょうか。
