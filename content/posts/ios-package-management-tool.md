---
title: "iOSのパッケージ管理ツールはどれが良いのか？"
date: 2021-02-07T01:14:20+09:00
draft: false
tags: ["iOS", "CocoaPods", "Carthage" ,"SwiftPackageManager"]
---

結論をいうと `CocoaPods` が良いかなと思います。

私のパッケージ管理ツールの変遷としては、まず`CocoaPods`を数年利用していました。  
その後は、`CocoaPods`と`Carthage`を併用していて、ライブラリの整備が完了した時点で完全に`Carthage`に移行しました。  
Xcode12からは一手間加えないと`Carthage`が利用できなくなってしまったので、いい機会だと思い`Swift Package Manager`に移行しました。  
２ヶ月くらい使ったのですが、`CocoaPods`に戻ることにしました。

個人的に使ってみた感じのそれぞれのメリットデメリットを記載します。

## [CocoaPods](https://github.com/CocoaPods/CocoaPods)

**メリット**

* ライブラリをgit管理しておくと、cloneしただけでビルドができる

**デメリット**

* xcworkspaceができてプロジェクトが汚染される
* ビルドに時間がかかる
* `CocoaPods`の初期化に時間がかかる

## [Carthage](https://github.com/Carthage/Carthage)

**メリット**

* `CocoaPods`と違いプロジェクトが汚染されない
* ライブラリは事前にビルドされるので、プロジェクトのビルドが早い

**デメリット**

* ライブラリをgit管理していても、ビルドする時に`Carthage`が入っていないとビルド出来ない
* Swiftのバージョンが上がるたびにエラーが出る(SwiftのABIが安定したので解決してるかもしれない)
* Xcode12からは一手間加えないとビルドが通らない

## [Swift Package Manager](https://swift.org/package-manager/)

**メリット**

* Xcode標準でサポートしているので、ライブラリの追加削除が簡単

**デメリット**

* ライブラリをプロジェクトと一緒にgit管理ができない


商用プロジェクトの場合は、ライブラリをgit管理できない`Swift Package Manager`のリスクは大きいかなと思います。  
実際に、ある企業が出しているiOS向けのライブラリで使っていたのですが、利用しているtagが消えて大騒ぎしたことがあります。  
デモプロジェクトで使う分には、簡単にライブラリを組み込めるのでおすすめです。

商用利用するとなると`CocoaPods`か`Carthage`かと思いますが、`Carthage`の場合はビルド時に必要なので、開発とは別のPCでクローンしてビルドしようとした時にすぐに動かせないことがあります。  
プロジェクトの汚染が我慢できるなら`CocoaPods`が一番手軽で安全だと思います。



