# 【第15週】ブルーベリー本輪読会🫐🫐<br />(2022-09-17)

[![hackmd-github-sync-badge](https://hackmd.io/kiTyD-EKRPG4ik3KEWbpRg/badge)](https://hackmd.io/kiTyD-EKRPG4ik3KEWbpRg)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-09-17（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係

- 前半
    - @haruguchi-yuma
- 後半
    - @haruguchi-yuma 

### ドライバー
- 前半
    - @cafedomancer
- 後半
    - @Maeda8 

### 読んだところ
- p.166 コラム18　「読み取り専用プロパティの部分型について」

### 次回
- p.175 4.5「変数スコープと関数」

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- @cafedomancer 
    - オブジェクトの readonly は歴史的経緯でガバガバ？
    - > TypeScript では変数の作成時にその変数の型が決まる
    - unknown 型はあらゆる型の subtype / any 型はあらゆる型の supertype (あれ、どっちがどっち？)

- @haruguchi
    - `T[]`は `readonly T[]`の部分型
    - オブジェクトの場合もそうなんだけど、部分型じゃないやつを代わりに使ってもコンパイルエラーでない
    - ジェネリクスはないと大変！
    - unknown型になったら型注釈を足す！

- @Maeda8 
	- T[]はreadonly T[]型の部分型
	- オブジェクト型に関しては普通のオブジェクトを受け取る関数にreadonlyプロパティを持つオブジェクトを渡してもコンパイルエラーにならないという罠がある
	- ジェネリクスは型引数を受け取る関数を作る機能
		- 型引数は省略できる

- @AntiSatori
    - 変数に型が決まるのは変数に作成時なので文脈による型推論は出来ても変数の使われ方による型推論は出来ない。

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @cafedomancer
    - 参加者が 5 人も！ 👯
    - RubyKaigi 以降 OSS 活動ができてたのしい 🙃
        - 何やってるんですか？
            - https://github.com/puma/puma/pulls?q=author:cafedomancer

-　@haruguchi
    -　８月以降一番人多い！
    -　 ruby `3 / 2 #=> 1`

- @Maeda8 
	- Integer / Integer #=> Integer
		- Floatじゃない
            - ![](https://i.imgur.com/ZIK61Rl.png)
            - ![](https://i.imgur.com/GvMm89J.png)
            - ![](https://i.imgur.com/RkWc22I.png)
	- トミーさんがやっときてくれた
	- AntiSatoriさんもきてくれた
