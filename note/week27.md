# 【第27週】ブルーベリー本輪読会🫐🫐<br />(2023-02-04)

[![hackmd-github-sync-badge](https://hackmd.io/H6-Kq8EjRZSojbjlo4p7fQ/badge)](https://hackmd.io/H6-Kq8EjRZSojbjlo4p7fQ)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2023-02-04（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係

- @eatplaynap 

### ドライバー

- @haruguchi-yuma 

### 読んだところ

- p.290 6.5.2 as constの用法

### 次回

- p.295 anyに近いが安全なunknown型

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- @haruguchi
    - anyはやばい
    - jqueryもやばい
    - しごと楽しむのはそれなりにあれ

- maimu
    - `any` 型はとにかくやばいということを覚えた
        - 型チェックと恩恵が受けられなくなり、プログラムの安全性の責任をプログラマーが負う（怖）

- @eatplaynap 
  - 子はTS化されているけど親がJSのままのVueコンポーネントで、propsとして受け取った値に対し、子側で無理矢理型をつけたというコードを昨日読んだ。中身ちゃんと理解してなかったけどas constを使っていたのかな？
  - 今コードを読んだらas 型で変換されていました

- @Maeda8 
	- 配列の値から型を作る方法を学んだ
		- `const array = ["piyo"] as const`
		- `type Hoge = typeof array[number]`
			- numberがキーなので上記のようなことが可能になっている!!
	- anyを使うとコンパイラが機能しなくなる
	- ユーザー定義型ガード説明できないことがわかった

- @AntiSatori
    - as constの役割を理解してなかったがよく分かった
        - 配列をタプルに
        - オブジェクト型をreadonlyに
        - 文字列とテンプレート文字列をwidningしないリテラル型に
    - any型の扱いは難しい　JSの自由な関数に型をつけるのも難しい

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @haruguchi
    - 今日も本が進んでよかった
    - このあと寝るかどうか問題
        - シエスタ
    - 何か作りたい(からつくる)

- maimu
    - FBCのもう一人の前田さんからrdbgを使ったデバッグのやり方を教えてもらいました。
        - メールとか非同期の処理をデバッグしたい時に便利に使えそう

- @AntiSatori
    - この章が終わったらTypeChallengeも始めたい
    - 午後はlefさんと一緒にReactやります

- @eatplaynap 
    - 人生は厳しい
    - 仕事じゃないプログラミングは楽しい

- @Maeda8 
	- 久しぶりに多くの人が集まって嬉しい