# 【第10週】ブルーベリー本輪読会🫐🫐<br />(2022-07-16)

[![hackmd-github-sync-badge](https://hackmd.io/lbTvRO1lTvOw1F7tiw0f9g/badge)](https://hackmd.io/lbTvRO1lTvOw1F7tiw0f9g)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-07-16（土）

### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係
- 前半
    - @paru871 
- 後半
    - @cafedomancer 
### ドライバー
- 前半
    - @Saki
- 後半
    - @mae-da 

### 読んだところ
- p.114 「3.6 分割代入」 から p.122 「3.7.1 Dateオブジェクト」途中まで

### 次回
- p122 「3.7.1 Dateオブジェクト」 
	- > 日時データをプログラムで扱う際はISO 8601形式という...

### 自由に使う共有スペース

- 3段階ネストさせたバージョン
```javascript=
const nested = {
  num: 123,
  obj: {
    foo: "hello",
    bar: "world",
    baz: {
        piyo: "chicken" 
    }
  }
}

//一行で書かず形を↑にそろえると分かりやすい
const { 
    num, 
    obj: {
        foo, 
        baz:{
            piyo
        }
    }
} = nested;

console.log(num); // 123
console.log(foo); // "hello"
console.log(piyo); //"chicken" 

```

```javascript=
const arr = [{foo: "fuga"}]
const [{foo}] = arr
console.log(foo);
```

```javascript=
//空白詰めても問題なく動く
const [,foo,,bar,,baz] = arr;
```

### p. 119 ネストしたパターンにデフォルト値代入する例（インデント下げて見やすくした）
```typescript=
type NestedObj = {
    obj?: {
        foo: number
    }
};

const nested1: NestedObj = {
    obj: { 
        foo: 123 
    }
};

const nested2: NestedObj = {

};

const { 
    obj: { 
        foo: foo1 
    } = { 
        foo: 500 
    }
} = nested1;

const { 
    obj: { 
        foo: foo2 
    } = { 
        foo: 500 
    }
} = nested2;

console.log(foo1); // 123
console.log(foo2); // 500
```

### p.120 restパターンで取得する値がないとき`...restObj`には`{}`や`[]`が入る。
```typescript=
const obj = {
    foo: 123,
};

const { foo, ...restObj } = obj;
console.log(foo); // 123
console.log(restObj); // {}

const arr = [1, 1];
const [first, second, third, ...rest] = arr;
console.log(first); // 1
console.log(second); // 1
console.log(third); // undefined
console.log(rest); // []
// → undefinedではないことに注意！
```

### p.120 ネストしたオブジェクトはコピーされないコード例
```typescript=
const obj = {
    foo: 123,
    bar: {
        arr: [1, 2, 3]
    }
};

const { foo, ...restObj } = obj;
console.log(restObj);
// {
//   "bar": {
//     "arr": [
//       1,
//       2,
//       3
//     ]
//   }
// } 

// restObjの中身を書き換える
restObj.bar.arr.push(4);
console.log(restObj)
// {
//   "foo": 123,
//   "bar": {
//     "arr": [
//       1,
//       2,
//       3,
//       4
//     ]
//   }
// } 

console.log(obj)
// {
//   "foo": 123,
//   "bar": {
//     "arr": [
//       1,
//       2,
//       3,
//       4
//     ]
//   }
} 
// もとのオブジェクトである、objの中身も書き変わってしまってる。
// restパターンで取得したものはシャローコピーだということがわかる
```

### わからなかったこと・疑問など
- @mae-da 
#### p.117で配列の中にオブジェクトを用意して、そのオブジェクトの値を分割代入で取得する際に、配列の中身にオブジェクト以外に文字列や数値なども他に用意しておき、オブジェクトの値を取得するところでコンパイルエラーが表示されてしまう
```typescript=
const arr = [{ hoge: "hoge" }, "piyo"]
const [{ hoge }] = arr
// Property 'hoge' does not exist on type 'string | { hoge: string; }'.(2339)
// とコンパイルエラー？が表示される
console.log(hoge)
// => "hoge"
```
→ 取得してるものがオブジェクトということが保証されていないためコンパイルエラーが起こっている模様。

#### 梅本さん説明
`arr` の型は `({ hoge: string } | string)[]` になっているので、`const [{ hoge }] = arr` をしているところで最初の要素が `{ hoge: string }` であることを保証できないんでしょうね。`as const` をつけて tuple にするとエラーがなくなると思いますよ。

#### 対応
```typescript=
// tupleにすることで、1つ目にオブジェクト、2つ目にstringが入ってることが保証されるようになる。
const arr: [{ hoge: string }, string] = [{ hoge: "hoge" }, "piyo"]
const [{ hoge }] = arr
// → コンパイルエラーが表示されない
console.log(hoge) // hoge
```


### 各自の疑問点や気づき、学んだこと

- @cafedomancer 
    - 分割代入される変数には型注釈をつけられない
    - 配列の長さ < 配列パターンの長さのときは変数に undefined が入ってしまう
        ```typescript=
        const [nothing] = [];
        console.log(nothing); // undefined
        ```
    - rest に対応する要素がないときは、rest には空の(オブジェクト|配列)が代入される
    - `Date` クラスの API は最悪だな...。Java の `java.util.Date` 由来なんだろうか。ちなみに Java では `java.time` が新しく導入されている
    

- @mae-da 
	- 分割代入でプロパティ名と別の変数名で取得したい場合は`プロパティ名: 変数名`とすれば良い
	- ネストしたオブジェクトの値を取得するには、パターンをネストさせる必要がある
	- オプショナルプロパティで型を宣言した際、分割代入でデフォルト値を指定して値を取得するようにすると、`undefined`が入る可能性を排除して推論してくれる（narrowingという）
		- https://www.typescriptlang.org/docs/handbook/2/narrowing.html
	```ts
	type Obj = { foo?: number };
	const obj1: Obj = {};
	const { foo = 500 } = obj1
	// fooの型がnumber型になってる
	```
	- restパターンで取得するオブジェクトがないときはオブジェクトの場合、`{}`が、配列の場合`[]`が取得できる。（`undefined`じゃない）
	- ネストしたオブジェクトはコピーされないことに注意（sakiさんの説明がわかりやすかった）

- @haramura
    - 変数に分割代入する
        - `const { 変数名 } = オブジェクト`：オブジェクトのプロパティの値を、変数に代入
        - `const [　変数名 ]　= iterable(配列など)`：配列の要素を、変数に代入
        - 分割代入で代入された変数には、型注釈を付けられず、型推論で型が決まる
        - 代入しようとする値が、undefinedのとき、デフォルト値を設定することもできる
        - `...変数名`：新しいオブジェクトや配列を作る(ただし、浅いコピーなので、深いネストはコピーされず同じものを参照している...)
            - オブジェクトの中だと、分割代入されていない残ったプロパティを持つオブジェクト
            - 配列の中だと、記載されたインデックス以降の要素を持つ配列

- @paru871 
	- タプル型をもう忘れていました😥
		- タプル型（tuple types）とは、要素数が固定された配列型
		- タプル型の構文は、[ ]の中に型をコンマで並べて書くというものです。たとえば、[string, number]は2要素のタプル型であり、最初（0番目）の要素がstring、1番目の要素がnumber型という意味です。
	- 分割代入ではデフォルト値を指定する機能がある
		- オブジェクトパターンや配列パターンにおいて変数名のあとに= 式を付加することで使用できる
		- その変数にundefinedが入るとき、その代わりに=の右の式が評価されてその値が変数に入る
		- おもにオプショナルなプロパティ（➡ 3.2.6）を持つオブジェクトを分割代入するときに有用
		- デフォルト値はundefinedのみに対して適用される、nullに対しては何も行わない

- @Saki
    - 分割代入では、型の絞り込み(type narrowing)と言って、デフォルト値を`変数名 = `と書くことで指定できる
    - この変数にundefinedが入る時、代わりにデフォルト値が入る
    - restパターン
        - オブジェクトで残りのプロパティ、あるいは配列で要素、の数が余ってない時、オブジェクトだと`{}`、配列だと`[]`が返ってくる。`undefined`が返ってこないのは想像と違うので注意。
        - 前にp.82-83あたりでオブジェクトは浅いコピーを行うので、コピーしてもネストしている部分からはコピー元とコピー先両方変わってしまう(共通)と学んだので、`rest`もそうかなと思ったら、やはりそうだった。オブジェクトのコピーは油断できない!

### 本日の振り返り(よかった点・次回に向けての改善点等)
wakariyasui
- @Saki
    - 【CM】**7/25(月)18:00~** パRailsの輪読会を始めるので、興味ある方ぜひのぞきにきてください〜☺️
    [パRails輪読会\(開催概要\) \- HackMD](https://hackmd.io/rOcLR0riRqmOgEF0_Ssm0A?view)
        - きになります！覗きに行きます〜！
    - どなたかHackMDで共同メモを作る方法を教えてくれませんか...
- @cafedomancer 
    - 変数名と値が結構適当。`{ bar: "string" }` とか

- @paru871 
	- 分割代入のデフォルト値の指定でネストしたパターンのところが盛大に混乱して意味不明になりましたが、形を整えてもらうことで理解出来ました！

- @haramura
    - 分割代入がじょじょに便利だと感じてきました！
        - ジョジョ？ 便利だと感じてきたんじゃあないか？

- @mae-da 
	- `;`（セミコロン）を忘れてしまう（梅本さんはセミコロン警察）
        - `(;;)`
