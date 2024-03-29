# 【第34週】ブルーベリー本輪読会🫐🫐<br />(2023-04-22)

[![hackmd-github-sync-badge](https://hackmd.io/ZRbOwHj_ScG5Z918vn4gRQ/badge)](https://hackmd.io/ZRbOwHj_ScG5Z918vn4gRQ)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2023-04-22（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係

- @haruguchi

### ドライバー

- @maeda

### 読んだところ

- p.352 「8.2.4 同期処理と非同期の順序」

### 次回

- p.360 「8.3.5 Promise の静的メソッド(1)」 から

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- @haruguchi
    - 今日は非同期について学んだ！
    - Promiseの話がいっぱいあった
    - 楽しかった。
    - https://scrapbox.io/haruguchi/Promise_finally%E3%81%AE%E7%89%B9%E5%BE%B4

- @Maeda8 
	- タスクキューとマイクロタスクキューの処理の順番を視覚的にイメージできた（https://www.jsv9000.app/ を使用して）
		- https://twitter.com/sakamoto_582/status/1648974355723083776?s=20
		- これをみんなでやった
	- 普通の非同期処理とPromiseを使った非同期処理を混在すると、思ったような処理の順番にならない場合がある。その際はPromiseベースで書き直したりする選択をとることもある？
	- Promiseを返す非同期処理で失敗時は何がくるかわからないので、unknown型を指定するのが良い

- まっきー
    - 非同期処理についてとても勉強になった
    - タスクキューとマイクロタスクキューの２つが存在すること、後者が先に呼ばれること（前者はそれまで放置プレー）
    - JSビジュアライザーで視覚的に順序が見れるのがよかった
    - ドライバーの方が確認してくれるので理解しやすかった
    - エラーはany型で受けるのは仕方がない
    - haruguchiさん紹介のzenn本も読んでみたい

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @haruguchi
    - この輪読会はゆるく深ぼっていく輪読会
    - 早朝輪読会に出ようと思って昨日は早く寝たのに寝坊した。起きたのは9:00
    - Maedaさんのドライバー捌きが良かった
    - まっきーさん参加してくれた。

- まっきー
    - 初参加でしたが、とても丁寧に深掘りしてくれるのですごくありがたかった
    - 終盤だから参加すべきか迷ったけど、参加してよかった🙌

- @Maeda8 
	- Promiseを返す関数を作った経験がほとんどないな・・・と思いました
	- まっきーさんと梅本さんが参加してくれた:+1: