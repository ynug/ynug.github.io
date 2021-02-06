---
title: "SwiftUI Tutorials を試してみました！"
date: 2021-02-06T00:39:22+09:00
draft: false
tags: ["iOS", "SwiftUI"]
---

Apple公式で公開されている [SwiftUI Tutorials](https://developer.apple.com/tutorials/swiftui/) を試してみました。

触ってみた感じとても簡潔にかけて、プレビューを見ながらデザインできるので Storyboard には戻れなくなります。

チュートリアルで使った部品を使って、郵便番号を調べるアプリを試しに作ってみました。  
[https://github.com/ynug/PostalCodeSwiftUISample](https://github.com/ynug/PostalCodeSwiftUISample)

キーワードから検索した際に、郵便番号の1桁のみで検索をかけた場合1万件位ヒットします。  
表示自体は問題ないのですが、再検索を行おうとした際にフリーズして動かなくなります。

郵便番号を4桁くらい入力して検索結果件数が少ない場合は、再検索を行っても問題はありませんでした。  

使い方が悪いのかListのバグなのか良くわかりません。  
実装の問題であればぜひ PR をお願いします！


都道府県から調べる
<img src="/img/tried-swift-ui-tutorial-1.png" style="border:solid 5px #e6e6e6"/>

キーワードから調べる
<img src="/img/tried-swift-ui-tutorial-2.png" style="border:solid 5px #e6e6e6"/>