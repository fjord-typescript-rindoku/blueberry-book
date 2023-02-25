# 【第29週】ブルーベリー本輪読会🫐🫐<br />(2023-02-25)

[![hackmd-github-sync-badge](https://hackmd.io/31s23sDPS2aPuviuOyv-PQ/badge)](https://hackmd.io/31s23sDPS2aPuviuOyv-PQ)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2023-02-25（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係

- @Maeda8 

### ドライバー

- @haruguchi

### 読んだところ

- p.303 可変長タプル型

### 次回

- p.316 7.1.1 変数のエクスポートとインポート

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- maimu
    - 難しかった！
        - 自分で `mapped types` や `condtional types` を使いこなすには理解が足らなすぎるので、組み込み型をちゃんと使えるようになりたい（ここも怪しい）
    - `^?` が今日一番の学び👶🏻

- LEF
    - 自分一人では分からないところを解説いただけて、とても助かりました！　ありがとうございます✨
    - `("S" extends "S" | "A" ? "S" : never) | ("A" extends "S" | "A" ? "A" : never) | ("B" extends "S" | "A" ? "B" : never)`について後でZennのコメント欄でお知らせしようかな……👀 :+1:

- @haruguchi
    - ラグザイア
    - mapped types は慣れ！
    - conditional types も 慣れ！
    - パッと例が出てこないのでまだまだだなと思いました。

- @Maeda8 
	- conditional types
		- `X extends Y ? S : T`
		- XがYの部分型ならばS、そうでなければT
		- Xの部分にユニオン型を渡すと渡したユニオン型すべてYの部分型かどうかみてくれる
		- https://zenn.dev/oreo2990/articles/1040312d7af066#1-2-union-distribution(%E3%83%A6%E3%83%8B%E3%82%AA%E3%83%B3%E3%81%AE%E5%88%86%E9%85%8D)
			- イメージしやすかった！
	- 組み込みの便利な型はmapped typesやconditional typesを使って作られている

- @AntiSatori
    - Type Challengeしてただけなので、可変長タプル型に関しては知らないことが多くて収穫があった。 
    - Homomorphic mapped typeが何なのか気になる

### 本日の振り返り(よかった点・次回に向けての改善点等)

- LEF
    - 今日はRuby 30周年イベントを視聴するので、リーダブルコード輪読会はお休みです。🙏

- maimu
    - 今やってるPJでバグを50個くらい見つけていてリリース間に合うんか・・・お腹痛い・・・な日々です😇
    - 読んだら鍛えられたgemとか皆さんありますか？（修行！！）
        - wataさんのgemが面白そうでした！https://wata00913.hatenadiary.com/entry/2023/02/01/084023
            - バグも少しあるらしいので、IssueやPull Requestを上げると良いかもです！
        - 修行という意味？　ActiveRecordだけど、マジで読めない
        - ちっちゃいgemとかがいいかも。fjordbootcamp生が作ったgemなら小規模なのでいいかも。コードレビューが入ってるやつ。
        - この中から作りやすそうなやつ選んで作ってみたらどうですか？　https://build-your-own-x.vercel.app/


- @Maeda8 
	- 6章が終わった:tada:
	- わからないことがわからない、チェリー本輪読会時代を思い出しながら読んでました

- @haruguchi
    - ラグザイア!!
    - 型に踏み込んでいくと圏論にたどり着く、、、つら、、、
        - HaskellやってTAPL読みましょう！（出来てない。。。）
    - もうすぐ3月なので、ECMAScript地獄からようやく解放される

- @AntiSatori
    - ゲームしてて寝不足ですが今日こそ@lefさんへのレビュー返信終わらします
        - 何のゲームをプレイされているかすごく気になります！🎮
            - MTGA https://mtg-jp.com/mtgarena/
