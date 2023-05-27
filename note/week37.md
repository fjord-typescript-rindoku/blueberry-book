# 【第37週】ブルーベリー本輪読会🫐🫐<br />(2023-05-27)

[![hackmd-github-sync-badge](https://hackmd.io/324joc5MQiCJuVHjYNy66Q/badge)](https://hackmd.io/324joc5MQiCJuVHjYNy66Q)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2023-05-27（土）

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

- @Maeda8 

### 読んだところ

- p.374 「8.4 async/await構文」 から 

### 次回

- p.380 「コラム38 top-level await」 から

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- maimu
    - `async` は関数
        - `async` 関数の返り値は必ずPromiseになる
        - 関数内で `return` が実行されるとその返り値がPromiseの結果となる
    - `async` 関数の返り値の型注釈は省略して推論させることも可能
        - 返り値は必ずPromiseなためPromise以外の型を書いた場合はコンパイルエラーになる
    - `await`　は式
        - `await` は「待つ」と覚えがちだけど、処理が止まるわけではなく同期処理は実行されている

-

- haruguchi
    - 電子レンジでチンする時別のことをしたい、つまりそういうことだ！
```javascript!
async function 料理() {
　　　　...
  await 電子レンジでチン()
 　 await チンした具材でなんかする
  ...
}
  
YouTubeみる
```

- @Maeda8 
    - async関数自体は非同期処理を行ってくれるものではなく、awaitがあることで、その`await 式`の式の部分を非同期処理で処理してくれる
        - なので、async関数のawait使う箇所までは同期的な処理が走ってる（個人的に勘違いしていた部分なので注意・・）
    - awaitはその処理を使って次に処理を進めたい場合・その処理（非同期処理）を行っているうちに同期的な処理を進めておきたい場合の大きく分けて2つの用途がある
    - 下記の場合（中の処理でPromiseをラップしてる場合）はget3が型推論してくれないので型を書く必要がある
```typescript=
async function get3(){
  console.log(“get3が呼び出されました“)
  return new Promise(resolve => resolve(“piyo”))
}
```

### 本日の振り返り(よかった点・次回に向けての改善点等)

- haruguchi
    - 最近毎日6000歩目標に歩いています。(雨天中止)
        - すごい👀
    - オブジェクト指向設計実践ガイド vs gemの再実装　vs メソッドツアー
- maimu
    - パーフェクトRubyを読んだら、前に全然理解できなかったブロックの仕組みが分かったような気がする
    - コード書きたいけど、企業研究とか調べ物が多くて最近全然書けていないです・・・
        - 時間の使い方が難しい

- maeda
    - AtCoderの色を変えるのはすごい大変だということがわかった
        - Dまで安定して解けたら緑
        - 灰色→茶色→緑
        - B問題が5分くらいでできたら茶色（haruguchiさん調べ）