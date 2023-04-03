# 【第31週】ブルーベリー本輪読会🫐🫐<br />(2023-04-01)

[![hackmd-github-sync-badge](https://hackmd.io/Ie5M9DzTTT-KuM4Jh2MtAg/badge)](https://hackmd.io/Ie5M9DzTTT-KuM4Jh2MtAg)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2023-04-01（土）

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

- p.325 7.1.4 型のインポート・エクスポート から 

### 次回

- p.334 コラム36 から

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- haruguchi
    - scriptはスコープが広くてやばそう
    - import や　export を明示的に記述するとmodule扱いになる


- @Maeda8 
	- 型としてimportしてるものは、import typeと明記するのが読みやすそう
	- 再エキスポートされる場合がよくわからなかった（ちょっと読みにくそう）
	- スクリプトでは定義された型や変数のスコープがプロジェクト全体になる
		- node.jsの環境ではmoduleとして使用されるので、新鮮だった
	- commonjs→Node.jsで使用できるモジュールシステム
		- Node.js環境でESModulesを使用したい場合（import構文使いたいとか）は、拡張子をmjsに変えるか、package.jsonにtype: "module"を追記する必要がある
	- 環境によって用意されてるAPIが違う（ブラウザ、Node.js）

- @AntiSatori 
    - JS、TSのファイルにはスクリプトとモジュールの二種類がある。
    - スクリプトではトップレベルに定義された変数のスコープがプロジェクト全体共有されるため注意が必要、モジュールでのスコープはファイル内のみ。
    - JSのモジュールシステムは標準のESModuleが出来るまでに独自で作られたものがいくつかあって使われておりややこしい。
    - CommonJS（NodeJSが非公式に採用されたモジュールシステム）
    - [AMD](https://en.wikipedia.org/wiki/Asynchronous_module_definition)

### 本日の振り返り(よかった点・次回に向けての改善点等)

- haruguchi
    - もうすぐ7章終わるぜ！
    - 3月中にβ版更新されたので研鑽Ruby読み直そうと思ったら4月になってた、そしてもうすぐ正式版がリリースされる？

- @Maeda8 
	- JSは奥が深い
	    - 横にも広い！
	- 今日は天気が良さそう

- @AntiSatori
    - JSの歴史は複雑で面倒くさい
    - Reactのドキュメントがベータから正式になったので読まないと　https://react.dev/
