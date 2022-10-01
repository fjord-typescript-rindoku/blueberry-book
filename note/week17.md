# 【第17週】ブルーベリー本輪読会🫐🫐<br />(2022-10-01)

[![hackmd-github-sync-badge](https://hackmd.io/p1d4hHShRGirK_b98Xv4mw/badge)](https://hackmd.io/p1d4hHShRGirK_b98Xv4mw)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-10-01（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係

- @cafedomancer

### ドライバー

- @haruguchi

### 読んだところ

- p.185 第5章「TypeScriptのクラス」 から

### 次回

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- @haruguchi
    - クラスフィールド（プロパティ）はnew演算子が呼び出されるたびに評価される
```javascript=
class User {
    foo: boolean = (() => {console.log('bar'); return true;})();
}

new User(); //=> bar
new User(); //=> bar
```

- @cafedomancer
    - コンストラクタの引数がない場合は `new User` のように `()` を省略できる
    - tree shaking とは、使っていないコードを削除する機能のこと
    - コンストラクタの引数にアクセシビリティ修飾子を付けると、プロパティを宣言することができる

- @Maeda8 
	- クラス内でのプロパティへの代入はnewを実行した際に評価されている
	- コンストラクタ引数名にアクセシビリティ修飾子をつけることで、プロパティの宣言と初期値の代入を宣言できる（わかりにくいけど）
	- 即時実行関数は関数の宣言と実行を同時に行なっている
	- member（メンバ）→クラス内でのプロパティとメソッドのことを指す（JS特有？）
	- クラスは関数オブジェクトらしいけどよくわかってないので勉強する

```javascript=
const User = function (name, age) {
  this.name = name;
  this.age = age;
  return this;
};

User();
new User();

class User {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

// User();
new User();
```

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @Maeda8 
	- 英語難しい！自分で訳してみようとすると、すごく頭を使う・頭働く
        - エラーメッセージを読めるようになろう！
	- 自分はTSというより、JSを勉強するべき
        - いい教訓ですね！ いいけど、行ったり来たりするのがいいと思います。TypeScript-ready なほど JavaScript をマスターできている状態とはどんな状態かを定義できないと思うので

- @cafedomancer 
    - 今日は北海道にいますよ！ 京都はめちゃくちゃ人がいました。懐石料理を食べてすかんぴんになりました
        - money is 大事
    - そろそろ冬で、ランニングもできなくなりそうだからジムに通おうかなあ...
    - はるなさんが槍玉に挙げられていてかわいそうｗ

- @haruguchi
    - 前田さんはharunaさんのせいでxxxxだった！
    - 寿司打やっとプラスになった 540円
    - 睡眠大事
    	- 🍮
    - 運動不足なのでランニングしたらいきなり過ぎて体負傷した、、、もう若くない
        - ストレッチとか準備運動とかウォームアップがめちゃくちゃ大事ですよ！！ クールダウンも