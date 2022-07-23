# 【第11週】ブルーベリー本輪読会🫐🫐<br />(2022-07-23)

[![hackmd-github-sync-badge](https://hackmd.io/KN2zD9QwTkOl1MFMTxEeQA/badge)](https://hackmd.io/KN2zD9QwTkOl1MFMTxEeQA)

###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-07-23（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係

- 前半
    - @haruguchi
- 後半
    - @mae-da 
### ドライバー
- 前半
    - @SatoshiHaramura
- 後半
    - @cafedomancer 

### 読んだところ
- p122 「3.7.1 Dateオブジェクト」 から p.129「3.7.5 プリミティブなのにプロパティがある?」 終わりまで

### 次回
- p.135 「第4章 TypeScriptの関数」 から

### 自由に使う共有スペース

### わからなかったこと・疑問など

```typescript=
const result = 'Hello, abbbbbbbc world! abc'.match(/a(?<worldName>b+)c/)
if (result !== null) {
    console.log(result.groups)
}
// Cannot read properties of undefined (reading 'replace') 
```
TSだとエラーが出るのが謎
NodeやChromeでは出なかった
playground側の問題ということがわかった(森塚さんのおかげで)

### 各自の疑問点や気づき、学んだこと

- @haruguchi
    -  ISO8601のZは世界協定時（UTC）を表すとわかった
    -  正規表現は伊藤さんのQiitaのやつがわかりやすかったなー
    -  プリミティブな値である'foo'とかもlengthプロパティを持っていると判断される（暗黙の型変換によって）
    -  だから、{length: number}みたいなtype alias作ったらその型を指定した変数に代入できる
    -  `{}`はnull, undefined以外のプリミティブ型を許容するので注意
        -  object型使っといた方が安全
    - 文字数を正確に数えたい場合はstringがiterable objectなことを利用して`[...str].length`とすればいい
- 

- @mae-da 
	- matchメソッドはgフラグがあるないで挙動が変わる
		- ない場合、第一引数に最初にmatchしたもの、第二引数にキャプチャしたもの
		- ある場合、第一引数にmatchしたもの全て
	- 名前付きキャプチャリングが実行できない（groupsプロパティが呼び出せない）のが気になった...
	- Setは集合を表すオブジェクト
	- `{}`型というものがある。（`object`型とは別）→`{}`は`null`, `undefined`以外の値を受け入れる
	- SetとWeakSet
	```ts
	const s = new Set();
	
	{
	  const obj = {};
	  s.add(obj);
	}

	console.log(s); // Set (1) {{}} 

	const ws = new WeakSet();

	{
	  const obj = {};
	  ws.add(obj);
	}

	console.log(ws); // WeakSet: {}

	```

- @paru871 
	- 協定世界時 (UTC)
		- [【みんなの知識 ちょっと便利帳】協定世界時（UTC）と日本標準時（JST）の比較対照と変換 \- 協定世界時（UTC）・日本標準時（JST）対照表](https://www.benricho.org/worldtime/utc_to_jst.html)
	- 正規表現リテラルにはフラグを付加できる、複数付加できる、igmsuyの6種類
	- testメソッド・・・string型の引数を受け取りboolean型の返り値を返すメソッド。与えられた文字列の中に正規表現の条件に合致する部分文字列が含まれていればtrueが返される。
	- matchメソッドにはキャプチャリンググループが使える、しかし、正規表現がgフラグを持っている場合はキャプチャリンググループは無視される。
	- Mapは真の連想配列、特定のキーに対して対応する値を保持できる
	- `Set<T>`は集合を表すオブジェクト
	- [Map/Set · JavaScript Primer \#jsprimer](https://jsprimer.net/basic/map-and-set/#map-and-set)
	
	
	

- @SatoshiHaramura
    - 日付データは、ISO 8601形式(`2022-07-23T15:00:00+09:00`)で扱う
    - 正規表現を扱うメソッド
        - 正規表現.test()
        - 文字列.match()
        - 文字列.replace()
    - Mapオブジェクトは、`キー`が任意の値(何でもOK)、値があり
    - Setオブジェクトは、`キー`のみ、値は無し
    - `{}`のオブジェクト型は、、

- @cafedomancer
    - 複数のコードポイントから構成される文字も `[...'🥹'].length` のようにすると文字数を適切にカウントできる。
    - プリミティブに対してプロパティアクセスを行うと、一時的にオブジェクトが作られる
        - 言葉が合っているか分からないけど、Java でいう autoboxing みたいなやつなのかな？
    - :point_up: の挙動にともなって`{}` や`{ length: number }` という型はプリミティブにもマッチする

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @Saki
    - 【リマインド】パRails輪読会が、いよいよ明後日の18:00~スタートするのでぜひ遊びにきてください〜
    ⏩詳細：[パRails輪読会\(開催概要\) \- HackMD](https://hackmd.io/rOcLR0riRqmOgEF0_Ssm0A?view)
		- :waiwai!:

- @paru871 
	- 今朝は自作サービスの初稼働で昨晩心配すぎてあまり寝られなかったため、今日は司会とドライバーをパスしてすみません🙏来週からは通常参加します💪
		- botの稼働無事うまくいったようでよかったです:+1::tada::tada::tada::tada:
			- ありがとうございます～～😭😭😭

- @mae-da 
	- チェリー本の輪読会で正規表現について色々学んだことを思い出した。また読みたい

- @haruguchi
    - 弱い〜とか、表現が面白かった。物理の世界とかでもよく強い〜とか弱い〜とか出てくる。
        - 強いAI, 弱いAI, とか
    - 昨日10時間以上車を運転したのでお尻がやばいです。そして今日も車検出しに行くので運転、、、😇

- @SatoshiHaramura
    - 先週1週間は輪読会に参加できていなかったので、徐々に生活リズムを整えて参加していきたいなと思います！
        - ジョジョ？

- @cafedomancer 
    - 雨だからやることないな...
        - パズルとか10000ピースくらい
        - 漫画とか！
        - ルービックキューブとか！
        - 映画！
        - 酒飲んで寝る！
