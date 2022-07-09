# 【第9週】ブルーベリー本輪読会🫐🫐<br />(2022-07-09)

[![hackmd-github-sync-badge](https://hackmd.io/zVam_-YGRN-VdcLubdKXyg/badge)](https://hackmd.io/zVam_-YGRN-VdcLubdKXyg)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-07-09（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係
- 前半
    - @mae-da 
- 後半
    - @Saki
### ドライバー
- 前半
    - @haruguchi-yuma
- 後半
    - @satoshi-haramura

### 読んだところ
- p.103 「3.5 配列」 から p.113 「コラム13 配列の要素にアクセスするときの密かな危険性」 まで

### 次回
- p.114 「3.6 分割代入」 から

### 自由に使う共有スペース



### わからなかったこと・疑問など

```typescript=
const arr = [0, 123, -456 * 100]
console.log(arr[0])
// 文字列でインデックスアクセスを行うとコンパイルエラーが出ると書かれていたが、コンパイルエラーでない。。
console.log(arr['0'])
```
→よくわからないので一旦保留

### 各自の疑問点や気づき、学んだこと

- @haruguchi
    - 配列型は要素の数は可変長 `T[]`か`Array<T>`と表す
    - `readonly　T[]`とすると要素の書き換えもできなくなる→便利そう
    - const やlet で宣言した場合 T[]型に推論される
    - タプル型は固定長の配列って感じ。亜種がたくさんあるけど、とりあえず基本系だけしっかり理解しておく。
    - タプル型で100個くらい要素がある場合記述するの地獄だなと思った
    - 配列のインデックスアクセスは危険。UnCheckedIndexedAccessつけれるならつけておこう

- @Saki
    - `const array = [1,2,3]`と、`const`を使って定義した時、`array = [4,5,6]`というように、 `array`を定義し直すことはできなくいようになっているが、`array[0] = 10`のように、配列の**要素**を変更することはいくらでもできる
    - そこで、TSは配列の要素の型を指定できる!
    - 指定方法は2種類
        - 1. `const array: number[] = [1,2,3]`:配列の要素は必ずNumber型。それ以外はコンパイルエラー
        - 2. 2個目のサンプルコード：「`name`キーしか受け付けない」 かつ 「値はString」のみ。
        - inuzukaさん曰く、後者はあまり見ないとのこと。
    - `const array:readonly number[] = [1,2,3]`と、`readonly`を付けると、配列の中身を変更できなくなる。中身を守れるの便利!
    - MDNは一次情報じゃなかった(けど信用できるドキュメント)
    - `for-of`文
      - `for (const elm of array)`できるのは、各ループで変数が作り直されるから、問題ないため。
      - `{ // 実行する処理}` の中で`elm`の値を変える場合は`let`でないといけない
      - (🤔基本`const`を使って、ダメだったら`let`を使えば安全そう？)
  - タプル型
    - 配列の要素の数が決まった配列型
    - `let 変数:[string, number]=["foo", 1]`と書くと、配列の1番目はstring、2番目はnumberと指定できる
    - ラベル付きタプル型は、エンジニアが読みやすいだけで`変数.name`みたいには呼び出せない(🤔それならオブジェクトでいい気がする...) 
        - 「オブジェクトだと自由に要素を追加できてしまうので、要素数を固定したい時はタプルが適している」とのこと
    - `[string,number,string?]`というように`?`を書くと、3番目はstring型の要素があってもなくても良いよ〜とできる
    - 可変長タプル型
  - TSの設定は、チームに入った時にちゃんとチェックしておいた方が良さそう。設定によって人がかくTSと自分が描くTSが全然変わってくる
  
- @paru871 
    - 配列型の記法、`number[]`はnumber型の値を要素に持つ配列を表す型
    - `T[]`と`Array<T>`という2通りの書き方ができる(流派？)
    - readonly配列型は読み取り専用配列型、`readonly T[]`と書く
    - MDNは2次情報だけど使える情報
    - for-of文で配列をループさせる構文が書ける
    - タプル型、要素数が固定された配列型、それぞれの要素に異なる型を与えることができる
    - 読み取り専用のタプル型、オプショナルな要素を持つタプル型、可変長のタプル型というものもある
    

- @mae-da 
	- 配列の型は`型[]`または`Array<型>`と指定できる
	- メモ：読み方`number[]`型 → 「number型の配列」（「numberブラケット型」と読むより良さそう）
	- タプル型：要素数が決まった配列型
		- `useState`も実はタプル型ということを知った
	- インデックスアクセスは型の不整合が起きてしまうため極力使用しないほうがいいとのこと
	- メモ：梅本さんが貼ってくれたtsconfigの設定
		- https://github.com/tsconfig/bases/blob/main/bases/strictest.json

- @SatoshiHaramura
    - 配列の各要素にも、型注釈を付けることができる
    - read onlyな配列型はあるけど、write onlyな配列型は無いということか...あったとして用途が無いのか
    - MDNは二次情報でも有用
    - 配列(iterable)の値を取り出すときは、for...of文を使うことを心がける
    - 基本形のタプル型は、要素数が固定された配列型

- @cafedomancer
    - `tsconfig.json` の設定次第で別言語になってしまうことを実感した
        - TypeScript で新規プロジェクトを始める場合はこういうのとをか設定したり参考にしたりするのがよいのかも... https://www.npmjs.com/package/@tsconfig/strictest
    - `React.useState()` の return type は tuple らしい
        - https://github.com/DefinitelyTyped/DefinitelyTyped/blob/master/types/react/v17/index.d.ts#L921
        ```ts
        function useState<S>(initialState: S | (() => S)): [S, Dispatch<SetStateAction<S>>];
        ```
        - tuple なんて使ったことないなと思っていたけど、React の custom hook を定義するときに無意識に tuple を使っていたような...！ (`as const` していただけかも)
    - MDN は 2次情報なのか！

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @haruguchi
    - 配列はいけそう！
    - したに口内炎？ができた:scream:

- @Saki
    - 配列の復習中心だったのでそこまで難しくなかった。
    - タプル使いこなしたい
    - 来週は分割代入😱

- @paru871 
    - 配列、前半はまだいけた！後半はどうかなー？

- @mae-da 
	- JSの内容が多め？の会だった！

- @SatoshiHaramura
    - なんとかついていけてる💦

- @cafedomancer
    - つかれていてねぼうした
    	- 🏃
