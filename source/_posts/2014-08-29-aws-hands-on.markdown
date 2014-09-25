---
layout: post
title: "【広島】AWSハンズオンに参加しました"
date: 2014-08-29 15:03:39 +0900
comments: true
categories: 
---

午後休をとって、[【広島】AWSハンズオン](https://atnd.org/events/55286)というのに参加してきました。

![jawsug_hr_logo](http://d3f9fl2jz5bc2k.cloudfront.net/wp-content/uploads/2014/08/jaws-ug_hiroshima.png)

<!-- more -->

#やったこと

### VPC（仮想プライベートクラウド）
- VPCを作成
- Internet Gatewaysを設定
- Subnetsでサブネットを設定
- RoutTablesで上記VPCをAttatch
- Security GroupsのInbound RulesでSSHを許可

### EC2（仮想サーバー）
- Key Pairsを作成、pemファイル保存
- Amazon Linux AMIをt2.microで作成
- TeraTermでローカルからSSH接続（上記pemファイルを使用）
- apacheのインストールと立ち上げ
- ローカルのブラウザからアクセス

### RDS（マネージドRDBサービス）
- mysqlを立ち上げ
- EC2側Security GroupsのInbound Rulesでmysqlを許可
- EC2からアクセス

### あとかたづけ
- 各種インスタンスの廃棄

# 感想
以前、ドットインストールの[Amazon Web Services入門 ](http://dotinstall.com/lessons/basic_aws)を一通りやったことがあるのですが、だいぶ忘れていました…

awsはweb上にドキュメントがしこたまあるのですが、やっぱり手を動かさないとピンとこないことが多いです。

参加者との交流ができなかったので、ちょっとさみしかったです。

[JAWS-UG 広島支部](http://jaws-ug.jp/bc/hiroshima/)では次回のハンズオンや勉強会を予定しているとの事だったので、また参加したいと思います。

