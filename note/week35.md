# 【第35週】ブルーベリー本輪読会🫐🫐<br />(2023-04-29)

[![hackmd-github-sync-badge](https://hackmd.io/Bza0svmeQZeAkpd3SxkQoQ/badge)](https://hackmd.io/Bza0svmeQZeAkpd3SxkQoQ)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2023-04-29（土）

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

- p.360 「8.3.5 Promise の静的メソッド(1)」 から

### 次回
5/20
- Promiseチェーン(1) チェーンを作る

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- maimu
    - `Promise.all` はよく使うらしい
        - `Promise.all` に与えられたPromiseが全て成功したら成功する
        - 与えられたPromiseのどれか一つでも失敗したら失敗する
    - `Promise.race` はPromiseの配列を受け取り、それらのうち最も早く成功または失敗したものの結果を、全体の結果として返す
    - Promiseの静的メソッド、全然知らなかった・・・上の二つを今日は覚えます

- @haruguchi
    - staticメソッドは型推論効くけど、普通のPromiseはコールバックの中の履行値までは面倒見てくれない
    - 引数は配列じゃなくても良いのか、忘れてた
- @Maeda8 
	- `new Promise`でPromise作成する際は、型推論が効かないため、自分で型を指定してあげる必要がある
		- `const promise = new Promise<number>((resolve) => resolve(100))`
	- Promise.raceの中の処理は先にthen以下のコールバック関数が実行されても、Promise.raceに渡した関数の処理は終わるまで実行されることに注意↓
```typescript=
const readFile = () => {
  return new Promise((resolve) => {
    setTimeout(resolve, 6000)
  })
}
const sleepReject = (duration: number) => {
  return new Promise<never>((resolve, reject) => {
    setTimeout(reject, duration)
  })
}

const p = Promise.race([
  // ファイルを読み込むのに6000m/sかかる処理
  // このファイル読み込みはsleepRejectが終わった後でも実行され続けることに注意
  readFile(),
  sleepReject(5000)
])
```

- LEF
    - Promiseについて復習できて良かったです！
    - all, any, race...
    - VSCodeでもTypeScriptの補完が効くようにしたい……
        - 拡張機能のなんちゃらってやつ入れれば、、、
        - RubyMineいいですよ！！
### 本日の振り返り(よかった点・次回に向けての改善点等)

- maimu
    - 自作サービスでほぼJS書かなかったため、どんどん忘れてます・・・
    - ブルーベリー本を最初からもう一度読み直します
    - チェリー本の次に読むといいRubyの本ってなんでしょう？
        - パRubyとか？
- @haruguchi
    - 次何やるの？ @maeda

- @Maeda8 
	- deviseのことはharuguchiさんに聞けば良い
	- サーバーサイドをnodeなどのフレームワークでやる人が出てくるのかもしれないという話をしました

- LEF
    - マリオの映画を観に行きたいです🍄