# 【第25週】ブルーベリー本輪読会🫐🫐<br />(2022-01-21)

[![hackmd-github-sync-badge](https://hackmd.io/X4jFgwNARbKaUcgiQEOqxw/badge)](https://hackmd.io/X4jFgwNARbKaUcgiQEOqxw)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-01-21（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係

- @haruguchi-yuma 

### ドライバー

- @maimu

### 読んだところ

- p.278 6.4 keyof型・lookup型

### 次回

- p.284 6.4.4 number型もキーになれる？

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- @Maeda8 
	- lookup型とkeyof型は、型に対して使う
		- lookup
			- オブジェクトの型が持つ値を型として得る
		- keyof
			- オブジェクトの型からプロパティ名の型を得る
			- 複数ある場合は、ユニオン型になる
	- ジェネリクス → 型変数
		- Map、forEachを自作するといい（haruguchiさん）
	- extends
		- A extends B→ AはBの部分型となる

- maimu
    - lookup型とkeyof型は型の再利用が可能
    - ジェネリクスを使うことで入ってきてほしい型を限定することができるようになる
    - `value: number, unit: keyof typeof mmConversionTable` のサンプルの部分は読んだだけだと？だったけれどharuguchiさんの解説込みで理解できた。
        ```
        keyof {　mm: number;　m: number;　km: number　}
        'mm' | 'm' | 'km'
        ```

- @haruguchi
    - 今日は勉強した
    - ここら辺は使い所が限定されててわからなくても大丈夫
    - でもTypeScriptは型の表現力が高いと言われる所以なので面白いところ
    - https://github.com/type-challenges/type-challenges やろう！
    	- waiwai!!

### 本日の振り返り(よかった点・次回に向けての改善点等)

-　@haruguchi
 - フィヨルドにはすごい人がいっぱいいるけど、腐らずがんばろう！
 -　最近モニター買いました！今日朝に設置しようと思ったけど、寝坊した、、、
 - kyoto.rbに行っていきます！

- @Maeda8 
	- 何かを作らなければ（手を動かさなければ）TypeScriptは理解進まないらしいので作りたい!!
        - 自作サービス作ってお金儲けよう!!!
- maimu
    - すごい人がいるとやる気出るタイプです🐣
    - 今、Reactを絶賛勉強中なので合わせてTypeScriptも書いて理解していきたい
