# 【第4週】ブルーベリー本輪読会🫐🫐<br />(2022-06-04)

[![hackmd-github-sync-badge](https://hackmd.io/u_FdcgdoTvGJ3iFLTKWxDA/badge)](https://hackmd.io/u_FdcgdoTvGJ3iFLTKWxDA)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-06-04（土）
### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00 （「わからなかったこと疑問」→「気づき」→「振り返り」の順で）

### 進行係

- 前半
    - @cafedomancer 
- 後半
    - @isshi

### ドライバー

- 前半
    - @mami-inuzuka
- 後半
    - @cafedomancer 

### 読んだところ

- p.42 「2.3.8 nullとundefined」 から p.53 「2.4.4 比較演算子と等価演算子」　まで

### 次回

- p.53 「コラム5」 から

### 自由に使う共有スペース

### わからなかったこと・疑問など

- p44の注釈22の意味がいまいちよくわからなかった
    - Numberは普通の関数としてもコンストラクタとしても使用できる
        - あ、コンストラクタとしても使えるというのはNumber(1)とかで数値の1を作れる的なこと...?
            - `new Number(...)` のことです。コンストラクタとしても使用できるというのは `new` 演算子を使えるということ。JavaScript のコンストラクタの実体は関数 (function object) です。
:naruhodo!:
- p.50の`++`や`--`を後ろにつけた場合の挙動の違いと、for文ではどちらにつけても結果が変わらなかった理由が分からなかったです...
    - `for (let i = 0; i < 10; i++)` だと `for (文; 式文; 式文)` だからですね
    - ```
      let a = 0
      let b = a++
      console.log(a, b) // 1, 0 返り値は変動前の値
      let c = ++a
      console.log(a, c) // 2, 2　返り値は変動後の値
      ```

- `x == null`は`x === null || x === undefined`とは厳密には同じではないところが気になったので自由研究したい 
    `document.all` って初めて見た :eyes: 
  	
### 各自の疑問点や気づき、学んだこと

- @haruguchi-yuma
    - 標準入力から受け取ったものはstringとして受け取る
    - number型とstring型を`+`演算子で連結するとnumber型は勝手にstring型に変換される
    - NaNはどんな演算をしてもNaNってなんか強いな
        - `NaN + 'string' // 'NaNstring'`だったからstringが強かった。NaNはnumber型だからか。
            - `String(NaN) + 'string'` になるんですね
    - `x == null`は`??`で代用できるのかな？と思った(条件分岐したい場合)
    - `''`から文字列は比較できない undefined

- @Saki
  - 最初のコードで`string`+`number`なのになぜ文字列結合してるの!?となったが、JSPrimerで暗黙的な型変換をやったのを思い出したので理解できた!
      - [暗黙的な型変換 · JavaScript Primer \#jsprimer](https://jsprimer.net/basic/implicit-coercion/#various-implicit-coercion)
  - RubyでString+IntegerしようとするとTypeエラーになるので違和感...(ボウリングで何度も見たエラー)
  - `Boolean("")`がfalseになる挙動がややこしい
  - RubyにはBoolean値のに変換する機能はない。`!`を使って値を反転する方法はある(🍒本2.5.2〜)
  - for文でなんとなく使ってた`++`は、インクリメント・デクリメントの演算子だった
  - stringの変数の前に`+`を使うと、数値と計算すると数値になるのは、挙動がわかってないとはまりそう
  ```js
  const str: string = '123'; //stringの型注釈をつけているが、
  console.log(+str * 100) //=> 12300 (+をつけると数値に変換される)
  ```
  - 最近`==`を使わない理由を忘れていたのでちゃんと理解できてよかった
      - `==`は、異なる型の間の比較をした場合、暗黙の型変換をしてから比較するためtrueになってしまうことがある
      ```js
      const str: any = "3"; //string
      console.log(str == 3); //=>true(numberに暗黙的型変換)
      ```
      - 梅本さんは、禁止されているわけでじゃないが、誰も`==`を使ってないとのこと
 

- @mae-da 
	- 空文字列をbooleanに型変換するとfalseになる
	- 標準入力で受け取ったものは文字列として認識するようになってる
	- `readline`ってなんかみたことあると思ってたらメモアプリで使ったのか！！
	- in演算子
		- >in 演算子は、指定されたプロパティが指定されたオブジェクトにある場合に true を返します。
		- [in 演算子 - JavaScript | MDN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Operators/in)
	- codePoint
		- >Unicodeはすべての文字（制御文字などの画面に表示されない文字も含む）に対してIDを定義する目的で策定されている仕様です。 この「文字」に対する「一意のID」のことをCode Point（符号位置）と呼びます。
		- https://jsprimer.net/basic/string-unicode/#code-point
	- JSの理解は大事（JSPrimer読まなきゃ） :合宿:

- @SatoshiHaramura
    - readlineで標準入力を受け取ると、文字列として受け取ることになる
    - `型推論`って、`型注釈`の記載が無いときに、`型注釈`を自動で判断してくれる機能
    - Number()で変換するときに、NaNになっていないか気をつける
    - `++`や`--`は、変数に使う。記載する位置によって、返って来る変数の値が異なるので気をつける

- @cafedomancer 
    - `BigInt('foooo')` で `SyntaxError` が起きるのが解せぬ
    - Node.js のコードは `@types/node` を入れないと動かなかったかも？
    - tsc でコンパイルする手順がさらっと省略されてたような？
        1. `npx tsc index.ts` 
        2. `node index.js` 
    - `undefined` との比較はいずれも `false` になるのかな？ (`==`, `===` を除く)
        - ![](https://i.imgur.com/kpLb4XB.png)
    - `in` たのしい！
        - ![](https://i.imgur.com/qug7pQf.png)
        - `0 in { 0: 1 }`

![](https://i.imgur.com/fhi3vJv.png)

- @obregonia1 
    - 言語によって型とかの仕様は微妙に違うので注意したほうがよさそう

- @mami-inuzuka 
    - x == null とすると xがnullまたはundefinedの時にtrueとなる
    - プログラムを書く時にどの型の値を扱っているのかをしっかり意識するようにしていこうと思った


### 本日の振り返り(よかった点・次回に向けての改善点等)

- @cafedomancer 
    - 今回はほぼ JavaScript の復習だった

- @mae-da 
	- 梅本さん司会・ドライバーやりながら読み手もやってた（読み手やりながらドライバーやってる人初めてみた）
        - 忙しくて楽しかったです！

- @haruguchi
    - TS要素はなかった。改めて読むと忘れていることが結構ある。
    - Maedaさんが3日でReactハンズオンラーニング読んだの聞いて震えてる
        - まえださんかわいそう
        - 理解度10%です

- @AntiSatori
    - JSの仕様の確認になった
    - 単項演算子のところが面白かった

- @SatoshiHaramura
    - JSPrimerを読んでいる最中なので、復習している感じでよかったです！

- @Saki
    - お開きの言葉はみなさんそんな気にしてないと思うので大丈夫ですよ〜
        - :souomou: :arigatougozaimsu::bow:
    - わからなかったこと・疑問なども最後に共有してもらえると嬉しいなと思いました(時間的に厳しいかもですが)
    	- 完全に忘れていました...:pray:（指摘ありがとうございます:pray:）
    	- 次回の初めに共有させて頂きます！:bow:
    	  - ありがとうございます!