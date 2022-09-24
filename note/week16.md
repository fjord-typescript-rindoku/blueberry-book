# 【第16週】ブルーベリー本輪読会🫐🫐<br />(2022-09-24)

[![hackmd-github-sync-badge](https://hackmd.io/bIIJFqOMQ1CMnrwoCt0n8w/badge)](https://hackmd.io/bIIJFqOMQ1CMnrwoCt0n8w)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-09-24（土）

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
    - @Maeda8 
- 後半
    - @Maeda8 

### 読んだところ
- p.175 4.5「変数スコープと関数」 から

### 次回
- p.186 第5章 から

### 自由に使う共有スペース

```javascript=

// function関数巻き上げあるのでこの位置でもOK
sum([1, 2, 3, 4, 5]);

function sum(arr: number[]) {
  let result = 0;
  for (var i = 0; i < arr.length; i++) {
    result += arr[i];
  }
  console.log(n);
  //=> undefined
  return result;
};

// 代入は指定した位置で実行されるので、巻き上げが起きた際のnの値はundefined
var n = 123;
```

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- @cafedomancer
    - for 文の変数は各ステップごとにコピーされる、ので環境も別々になる
    - JavaScript は言語としての進化がめざましくて面白い

- @haruguchi
    - for文で初期化した変数はブロックの処理が終わった後コピーされる
    - クロージャの知識使って読み解いたの初めてかも
    - setTimeoutはTask Queueに入ってCall　Stackが空になったら1つCall　Stackに連れて来られる

- @Maeda8 
	- スコープの内側と外側に同じ名前の変数がある場合、内側のスコープが優先される
	- for文のスコープクイズ楽しかった
		- 今日はJSの学習（クロージャー）をしたい

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @haruguchi
    - JS輪読会(TS)だった!
    - 次はクラスだ！

- @Maeda8 
	- 第4章ひとまず終えることができた。部分型のところが難しかった

- @cafedomancer
    - 1 個前の飛行機 (09:00) 、走ったけど間に合わなかった
