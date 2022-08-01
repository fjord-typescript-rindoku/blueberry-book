# 【第12週】ブルーベリー本輪読会🫐🫐<br />(2022-07-30)

[![hackmd-github-sync-badge](https://hackmd.io/qFjMkm2QT2uc42mSLVK8lQ/badge)](https://hackmd.io/qFjMkm2QT2uc42mSLVK8lQ)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-07-30（土）

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
    - @napple29 
### ドライバー
- 前半
    - @mae-da 
- 後半
    - @haruguchi

### 読んだところ
- p.135 「第4章 TypeScriptの関数」 から p.148最後まで

### 次回
- p.149 コラム15 「関数もオブジェクトの一種である」　から

### 自由に使う共有スペース
```javaScript=
> const func1 = (a = 1) => console.log(a);
undefined

> func1()
1
undefined

> func1(undefined)
1
undefined
```

rubyはnilを渡してもnilが入る
```ruby=
def hoge(a = 1)
    puts a
end

hoge
#=> 1
hoge(nil)

(↑nilがある)
```
### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと
- @napple29 
    - 関数宣言では巻き上げが起こる（他の書き方だと起こらない）
    - 引数に型がついてるから引数の数もJSと違ってガバガバじゃない
    - returnの後は改行すると`;`が補われてエラーになる
        - returnの後に`()`をつける
    -　固定長引数の関数にスプレッド構文を使いたいときはタプル型にしないとコンパイルするときに配列の中の数まで認識されなくてエラーになる
    -　普通の引数 -> オプショナル引数 -> rest引数の順番で書く
    -　デフォルト引数もできる
    

- @haruguchi
    - アロー関数はコンストラクタを作らない（それ以外はfunction関数式とできることは同じ）
    - BMIは単位に注意する[m]
    - return を書いた後に改行すると勝手にセミコロンを補われて死ぬ
    - 前田さんのモニターはブラウン管
    - 上にデフォルト引数にundefinedを渡した時の挙動を書いておきました。
    - 　スプレッド構文とてもとても便利

- @paru871 
	- 関数宣言の構文は`function 関数名(引数リスト): 返り値の型 { 中身 }`
	- 引数リスト`変数名: 型`
	- return文に対しても型チェックが行われる。
	- 関数宣言には巻き上げがある！(関数宣言よりも前にその関数が使える)
	- 返り値がない場合はvoid型を示す
	- 関数式
		- 関数はプリミティブではないのでオブジェクト
		- 関数式は関数宣言とは異なり巻き上げ機能は持たない
		- 構文は`function (引数リスト): 返り値の型 { 中身 }`
	- アロー関数式
		- 構文は`(引数リスト): 返り値の型 => { 中身 }`
		- 省略形の構文`(引数リスト): 返り値の型 => 式`
	- 配列の要素数の情報を型に残す・・・タプル型を使うと良い
		- 固定長引数の関数にもスプレッド構文が使える
		- タプル型の記述が面倒な場合は`as const`を使っても良い 

- @mae-da 
	- 関数宣言では巻き上げが起こる
	- 関数式・アロー関数式では起こらない
	- 関数式・アロー関数式のブロックの終わりには`;`が必要そう
		- https://jsprimer.net/basic/statement-expression/#function-statement-and-function-expression
	- 返り値がない関数を宣言する際は、返り値の型としてvoid型を指定する。
	- アロー関数の省略形で、返り値の式でオブジェクトリテラルを返したいときは、`()`で囲むことに注意する
	- JSでは引数を省略した場合、エラーではなく`undefined`が入る
		- https://jsprimer.net/basic/function-declaration/#function-less-arguments
		- `undefined`を明示的に渡してもいいという意味が理解できた:bow:

- @mami-inuzuka （ラジオなので飛ばしていただいて大丈夫です！）
    - いままでReactで特に意識せず使っていた`return()`だけどコラム14とharuguchiさんのコメントでそう言うことだったのかと腹落ちした
```javascript
// これは普通にOKな例
function returnOne(): number {
    return 1;
}

// これはreturnのあとに改行があるからreturn;だと認識されてundefinedがかえってしまう
function returnOne2(): number {
    return
        1;
}

// () があれば途切れていると認識されない
function returnOne3(): number {
    return (
        1
    );
}
```
- これまで残余引数（rest parameter）とスプレッド構文がごっちゃになってたけど今日だいぶ整理できた気がする...！
    - 残余引数と可変長引数は同じ意味？
        - 同じそう
            - > 引数の個数が決まっていない引数のことを可変長引数(variable length arguments, variadic arguments)といいます。JavaScriptでは可変長引数は残余引数(rest parameter)と呼びます。
            - https://typescriptbook.jp/reference/functions/rest-parameters
            - プログラミングの世界で一般的に可変長引数と言うけどJSの世界では残余引数（rest parameter）という言い方をする、ってことかな？
    - 引数を`function hoge(...params){}` と書くと何個でも引数を受け取ることが可能な関数を定義することができる
    - 残余引数に渡した引数達は配列に格納される
        - `hoge(1, 2, 3);` とすると paramsには`[1,2,3]`がはいる
        
    - 関数呼び出し時の引数にスプレッド構文を用いると配列が展開され順番に引数に渡される
```javascript
const num = [1,2,3]
fuga(...num)
//=> fuga(1,2,3) とするのと同じことになる
```

- @Saki
    - 可変長引数と固定長引数(4.1.8まとめ)
        - 可変長引数：`number[]`は、配列の要素がnumber型であれば何個でもOK。なので、`sum(...nums)`の`nums`を定義する時、「要素が3つ」等型注釈をつけなくていい。
        - 固定長引数
          - `const sum3 = (a: number, b:number,c:number) => a + b + c;`←これは、配列の要素がnumber型であることに加えて、要素数が3つであることを指定してる
          - ↑は要素数が必ず3つと指定しているので、`sum3(...nums)`の`nums3`を定義する時も`const nums [number, number, number] = [1,2,3]`のように、タプル型(要素数が決まってる配列)の型注釈を書くことで、「ちゃんと要素が3つの配列だよ」と明示している。`num3`を型注釈を書かずに普通に定義した時、たとえ要素数が3つでもコンパイルエラー：「a spread argument must either have a tuple type or be passed to a rest parameter(spread引数はタプル型であるか、restパラメータに渡される必要があります。)」と出る。
          - restパラメータ何でしたっけ...あとで調べます!
              - 可変長引数のことで任意の個数の引数を受け取れるやつ　`(...args)　=> {}`みたいな！ あ、違うかも
              - 残余引数か　　(a, b, ...rest) => {}

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @Saki
    - 寝坊しました🙏
    - 自作サービス、退会した人のレコードの扱いが難しいですね〜。DB設計難しい🤯
    - ↓ haruguchiさん来週からエンジニアデビューですね🎌🎊
  
-　@haruguchi
    -　8月になるぞ！
        -　お仕事の話また聞けるの楽しみにしてます :raised_hands: 

- @napple29 
    - ↑月曜から社会人のひと！！！🎉 :tada: :tada: 

- @paru871 
	- わー、はるぐちさんは無職最後の週末なんですね！楽しんでください✨✨
	- かわせさんがミートアップで教えてくれた漫画の「ラーメン赤猫」にハマりました😆

- @mae-da 
	- haruguchiさんがついに:tada:

- @mami-inuzuka 
    - 素朴な疑問でちょっと聞いてみたいのですが....輪読会によく参加している方々は勉強熱心な方が多いと思うのですが、みなさんが勉強したい！とおもう気持ちの源泉って何ですか？
    - 笑
