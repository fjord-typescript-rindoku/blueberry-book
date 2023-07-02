# 【第40週】ブルーベリー本輪読会🫐🫐<br />(2023-07-01)

[![hackmd-github-sync-badge](https://hackmd.io/hAJsvBoVToa-FE4jmqCubg/badge)](https://hackmd.io/hAJsvBoVToa-FE4jmqCubg)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2023-07-01（土）

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

- @まっきー
- @haruguchi
- @Maeda8 

### 読んだところ

- p.179 「4.6 力試し」 から

### 次回

- p.244 「5.6.3 力試し」 から

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

-　@haruguchi
    -　今日学んだことはクラスのフィールドは最初に型宣言しないとエラー出るってこと。

- @Maeda8 
	- 関数の返り値の型は推論させるのが推奨されている
	- `[Array(3)]`と`[...Array(3)]`は違う
		- 素な要素みたいな話
		    - 疎!
		    	- :bow:
		- `console.log([...Array(3)].map((_, i) => i))`
			- indexをmapで取得してる形
		- `console.log([...Array(3).keys()].map((i) => i))`
		- `console.log([...Array(3).keys()])`
			- 上の2つでも書ける！
	- map関数を自分で書く話
		- 渡される引数の型や、返り値の型に汎用性を持たせたい場合、ジェネリクスを使う
```typescript
function map(array: T[], callback: (arg: T) => U): U[]{
	//...
}

// ↓上記はこのように書ける
function map<T, U>(array: T[], callback: (arg: T) => U): U[]{
	//...
}
```

- まっきー
    - ...Array(3)と書くと[undefined, undefined, undefined]が生成される
    - これをmapで上書きしていく手法
    - mapの引数は1.値　2.インデックス　3.配列そのもの
    - 第一引数を使わないときは`_`とできる
    - TypeScriptのクラスではconstructorの前にフィールドの型宣言する
    - readonlyと#を組み合わせてより堅牢にできる
    - ジェネリクス（T,U）を使った書き方を使うと呼び出し側が型を決められる　←Reactのライブラリでも汎用性のために書かれているらしい

### 本日の振り返り(よかった点・次回に向けての改善点等)
- haruguchi
  - フロントエンド何もわからないからDOMの勉強しようと思っている(思っているだけ)
  - でも低レイヤーの勉強もしたいから大変。時間が欲しい。
  - 与太話しすぎた　後2回くらいで終わるかな。


- @Maeda8 
	- 自分も知能検査受けてみたいです
	- TypeScriptの良さを実感できて楽しいなと思いました（ジェネリクス）
	- 数学にもいろいろな世界がある

- まっきー
    - WAIS-Ⅳはぜひ受けてみたい
    - TypeScript、仕事でもすごい使われているので自分でもブルーベリー本読む