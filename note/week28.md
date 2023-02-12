# 【第28週】ブルーベリー本輪読会🫐🫐<br />(2023-02-11)

[![hackmd-github-sync-badge](https://hackmd.io/J6JClnvRRnybBlMqQZnW9A/badge)](https://hackmd.io/J6JClnvRRnybBlMqQZnW9A)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2023-02-11（土）

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

- @fuwa

### 読んだところ

- p.295 anyに近いが安全なunknown型

### 次回

- p.303 可変長タプル型

### 自由に使う共有スペース

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

p.297 「6.7.1 object型・never型」でのサンプルコードの解説（プリミティブ型を許容しないコード）

プリミティブ型は呼び出される時にラッパーオブジェクトとして暗黙的な変換がされるため、「オブジェクト型でxxxメソッドを持つもの。」という型を指定した際に、プリミティブ型のものが入ってくる場合がある。それを排除するため、object型を指定する（objectはオブジェクト型のみを指定する型）

```typescript=
type HasToString = {
    toString: () => string
}

function useToString(value: HasToString) {
    console.log(`value is ${value.toString()}`)
}

// toStringメソッドを持ったオブジェクト
// ※①とする
useToString({
    toString() {
        return "foo"
    }
})

// 3.14はNumber型でtoStringメソッドは持ってないのでダメそうに思えるが、
// 3.14は呼び出される際に、Numberのラッパーオブジェクトに暗黙的に変換されるためtoStringメソッドを呼び出せるのでOKになってる
// ※②とする
useToString(3.14)
```
```typescript=
// ①のようなものだけ（オブジェクト型）を受け入れるようにするため、object型を指定するようにする。
// ②のようなプリミティブがラッパーオブジェクトに変換されるようなのも排除する

function useToString(value: HasToString & object) {
    console.log(`value is ${value.toString()}`)
}

// 3.14はプリミティブ型で、Numberのラッパーオブジェクトに変換され、NumberはtoStringメソッド持ってるが、
// object型しか受け付けないようにしたため、エラーが出る。

useToString(3.14)// Argument of type 'number' is not assignable to parameter of type 'HasToString & object'.Type 'number' is not assignable to type 'object'.

// hogeはオブジェクト型で、toStringを持ってるからOK
const hoge = {
    name: "hoge",
    toString() {
        return "hoge"
    }
}

useToString(hoge)

// "piyo"はプリミティブ型で、Stringのラッパーオブジェクトに変換され、StringはtoStringメソッド持ってるが、
// object型しか受け付けないようにしたため、エラーが出る。

useToString("piyo") // Argument of type 'string' is not assignable to parameter of type 'HasToString & object'.Type 'string' is not assignable to type 'object'.

```

- maimu
    - プリミティブ型にもラッパーオブジェクトが存在するため、オブジェクトのみを許可したい場合に暗黙的に型が変換されてしまう
        - その場合は `& object` を用いて、オブジェクトだけが許容されるように制限することが可能
    - ユーザー定義型ガードは、型安全性を破壊する危険な機能だけど、 `any` や `as` を使うよりは選択肢として活用するのはあり
        - 関数を用いて型の絞り込みを行うことが可能
        - 書いた人が責任を持たなければいけないという点は `any` や `as` と同様


-　@haruguchi
    -　　 unkown :>any :> .... :> never
    -　　 ユーザー定義型ガード
```javascript!
function fn(foo: unkown): foo is type {
    return boolean( true or false )
}

function fn2(): asserts is type {
    // type でない場合を列挙し、throw Errorする
}
```

- @Maeda8 
	- ユーザー定義型ガードは関数
	- `引数名 is 型`
		- 処理の中でbooleanを返す処理をかく。trueを返す場合、型述語に書かれた型として受け取った引数の型を指定することができる
	- `asserts 引数名 is 型`
		- 処理の中で例外が発生しない場合、型述語に書かれた方として受け取った引数の型を指定することができる

- @fuwa
    - any型よりはマシだけどunknown型もやばそう。できるだけ使わないようにします〜
    - ユーザー定義型ガードはtrueを返したら型述語に書かれた型ををコンパイラに伝える

- @AntiSatori
    - ユーザー定義型をちゃんと書くにはJSで型を判定するためのロジックの書き方をきちんと理解する必要がありそう。
    - unknownとanyみたいな全ての型のスーパータイプはTop typeでneverみたいな全ての型のサブタイプはBottom typeと言うらしい。
    - https://en.wikipedia.org/wiki/Top_type
    - zodは型Aの変数を型Bの変数へと変換するための関数を定義できるライブラリ。

### 本日の振り返り(よかった点・次回に向けての改善点等)

- LEF（代読お願いします）
    - ここ数日朝起きられていて一日って長かったんだと実感しました🌅
    - リダブルコド先週日曜日は参加者5人で脱落者が、続出！📘(´；ω；｀)

- @fuwa
    - まだブルーベリー本を前半までしか読んでいないので全体的に難しかったです〜
        - 多分この本でここら辺が一番難しい？かも
            - そうなんですね！ここを乗り越えられればなんとかなる…？
    - これから賃貸の契約更新費用を振り込んできます。。貯金残高が悲惨なことに！
-　@haruguchi
    - 早起き成功したので寝ます！
    	- :sleeping_accommodation:

- maimu
    - 転職を見据えてスーツとかYシャツ買わないと・・・と思いつつ、証明写真くらいしか着ないのでは？と思うと買うの面倒くさいと思ってしまいます・・・
    - 今日こそスマホを買い替えます！
    - JS苦手族だったけれど、最近やっと学ぶのが楽しくなってきました！

- @Maeda8 
	- ユーザー定義型ガードの`assert`を使うのかっこいい。使ってみたい

- @AntiSatori 
    - 今週はTSの型システム集中的に勉強してFizzBuzz型作れるまでになりました
    - https://github.com/type-challenges/type-challenges/issues/23378
    - そのかわりにプラクティス進めれてない。。