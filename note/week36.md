# 【第36週】ブルーベリー本輪読会🫐🫐<br />(2023-05-20)

[![hackmd-github-sync-badge](https://hackmd.io/a8rBp1X1Qfej5x1Euk4mkw/badge)](https://hackmd.io/a8rBp1X1Qfej5x1Euk4mkw)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2023-05-20（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係

- @maimu

### ドライバー

- @Maeda8 

### 読んだところ

- p.366 「8.3.8 Promiseチェーン(1) チェーンを作る」 から

### 次回

- p.374 「8.4 async/await構文」 から

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- maimu
    - `then` `catch` `finally` などのPromiseメソッドは新しいPromiseオブジェクトを返す
    - `catch` はPromiseの失敗を成功に変換することができる
    - Promiseはチェーンで伝播していくため、エラーハンドリングも適切にしないとプロセスの強制終了につながってしまう
    - dynamic import構文は指定されたモジュールを非同期的に読み込んでいる
        - 普通のimport宣言との違いはdynamic importが実行されるまでモジュールの読み込みが行われないという点

- @haruguchi

  -　thenのコールバックの中でPromiseを返すと余分にマイクロタスクキューが発行されるのでPromise以外の値を返す場合と比べてキューに入るのが1つずつずれて面倒なことになるのは忘れてくれ！
  -　あとthenの中のPromiseでさらにチェーンをネストさせると頭が爆発する(良いこはしてはいけない)

https://zenn.dev/estra/books/js-async-promise-chain-event-loop/viewer/m-epasync-promise-prototype-then#%E8%A7%A3%E6%B1%BA%E5%80%A4%E3%81%AE%E9%81%95%E3%81%84%E3%81%AB%E3%82%88%E3%82%8B%E6%8C%99%E5%8B%95%E3%81%AE%E3%81%BE%E3%81%A8%E3%82%81

- @Maeda8 
	- thenメソッドの戻り値はPromise
		- then内で、Promiseチェーンをネストさせて、戻り値として文字列を返そうが、Promiseを返そうが、1つのPromiseが返ってくると理解しておけば良い
		- Promiseを返すPromiseは本当は意味があるらしい
	- then, catchでPromiseチェーンしているときに、thenメソッドは呼ばれてないわけじゃないらしい
		- thenメソッド内部で、Promiseがrejectなものでかつthenメソッドの第二引数にコールバック関数が登録されてなかったらcatchメソッドに渡す、みたいな処理が行われてる
	- dynamic importは、式じゃない文なので、関数呼び出しじゃない。予約語らしい

### 本日の振り返り(よかった点・次回に向けての改善点等)

- maimu
    - 他の言語のサンプルコードをRubyに書き換えるのは理解が深まりそうなため早速やってみたい
    - 本を買いすぎて本棚が収納の限界を超えているけど、新しい本が欲しい！
        - わかる！！！！
    - 面接対策が全く進みません！

- haruguchi
  - 前田さんの会社にいる人RubyKaigiで話してたけどとても面白かったですよ。Ruby.Wasmの話
  - JSと仲良くなりたいがほんとに厄介な言語だなと思う。

- @Maeda8 
	- ゼルダ楽しいけど、生活リズムが悪くなってきた
	    - 2日やって２日寝るのはどう？