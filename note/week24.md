# 【第24週】ブルーベリー本輪読会🫐🫐<br />(2022-01-07)

[![hackmd-github-sync-badge](https://hackmd.io/F5v5uge5TQqRPuUZ-bhlWQ/badge)](https://hackmd.io/F5v5uge5TQqRPuUZ-bhlWQ)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-01-07（土）

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

- p.266 6.2.3 ユニオン型とリテラル型を組み合わせて使うケース

### 次回

- p.278 6.4 keyof型・lookup型

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- @Maeda8 
	- 無理にwideningは発生しない
	```ts
	const a = "a"
	const b: "b" = "b"
	
	let c = a
	// stringにwideningされる
	// let c: string
	let d = b
	// stringにwideningされない！！
	// let d: "b"
	```
	- 共通のプロパティを持たせると、型の絞り込みを行う上で便利
	- 型の絞り込みを行いたいときは、タグ付きユニオンを使うのはベストプラクティスっぽい？
	- 愚直に型をかくとコンパイルエラーになる場合が多い
	- typeofの戻り値は文字列
	- switch文でdefault節がいらない話、breakを書かなくてもいい話がすごいためになった。まとめたい・・
	    - ブログかけ！学んだらかけ！

- maimux2x
    - typeof演算子を使うと `string | number` のようなユニオン型に対して型の絞り込みを行いたい場合に便利。
        - プリミティブ値がtypeof演算子に与えられると、その種類に応じて異なる値が返される。
        - オブジェクトの場合は関数かそれ以外の２パターンしかない。
    - TSで擬似的に代数的データ型を作るにはユニオン型の構成要素のオブジェクト型に「タグ」となるプロパティを付け加える。

- @haruguchi
    - 何にも覚えてないや
    - narrowing は if文(三項演算子), switch文 typeof演算子, 条件演算子でもできる
    - でもfoo && foo.bar したらESLintに怒られる(自分のプロジェクト)
    - if ( ) foo

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @Maeda8 
	- タグ付きユニオンあんまり見たことないといったが、自分が概念として持ってなかっただけでスルーしてるだけかもしれない
	- 輪読会EXPOもう少しだ。用意しないと！！

- @haruguchi
    - 正月で太った
    - 輪読会EXPOはアドリブでやるのでMaedaさんの方手伝えます
    	- :sugoi::arigatougozaimasu!!:
    - 森塚さんを久しぶりに観測した
    - この本ももうすぐ終わる???
    - モニター買うかずっと迷ってます

- maimux2x
    - ブートキャンプアプリの環境構築でwebpackのコンパイルエラーが解消できません・・・
        - おおお!チーム開発入られたんですね:tada: 