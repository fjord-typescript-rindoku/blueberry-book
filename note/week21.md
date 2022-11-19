# 【第21週】ブルーベリー本輪読会🫐🫐<br />(2022-11-19)

[![hackmd-github-sync-badge](https://hackmd.io/_TnAfC5aTZ286C1PqB4ERA/badge)](https://hackmd.io/_TnAfC5aTZ286C1PqB4ERA)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-11-19（土）

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

- p.225 「thisを操作するメソッド」 から

### 次回

- p.240 「コラム25 throwはなんでも投げられる」

### 自由に使う共有スペース
```typescript=
// 再帰でsum関数書くとこんな感じ
function add(nums: number[]): number {
    if (nums.length === 0) {
        return 0
    }
    // オペランドがnullかつundefinedではないことを保証
    // Non-Null Assertion Operator
    // https://typescript-jp.gitbook.io/deep-dive/intro/strictnullchecks#nullasshonnon-null-assertion-operator
    return nums.shift()! + add(nums)
}
```

```haskell
-- 関数型言語での例
sum :: Num a => [a] -> a
sum []     = 0
sum (x:xs) = x + (sum xs)
```

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- @Maeda8 
	- エラーが発生した際に指し示される箇所は、Errorオブジェクトが作られた箇所（知らんかった・・）
	- 失敗内容によって異なるエラー処理を行いたい位場合には、失敗を表す返り値を返す方が良い（undefinedを返すなど）
	- finallyブロックはエラーの発生の有無に関わらず処理が実行される
	- finallyはreturnからの大域脱出の場合でも呼ばれる

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @Maeda8
	- sum関数を再帰で作った
	- 再帰難しい・・・

- @AntiSatori 
    - いつも朝起きれなくて参加出来てなかったが今日は久しぶりに参加出来て良かった