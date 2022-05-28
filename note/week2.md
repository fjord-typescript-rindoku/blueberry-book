# 【第2週】ブルーベリー本輪読会🫐🫐<br />(2022-05-21)

###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- サンプルコードのダウンロード
[プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)

---
## 2022-05-21（土）
### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00

### 進行係
- 前半
    - @SatoshiHaramura
- 後半
    - @isshi-hasegawa 
### ドライバー
- 前半
    - @mami-inuzuka
- 後半
    - @obregonia1 

### 読んだところ
p.9 1.2.1　TypeScriptコンパイラの役割(1)型チェック から
> 上のプログラムではdoubleという....

~

p.31 2.2.3 変数に型注釈を与える 最後まで

### 次回
p.31 2.2.4 let による変数宣言と変数への再代入　から

### 自由に使う共有スペース

### わからなかったこと・疑問など
- @mami-inuzuka
    - TypeScriptつかうなら　Babelは不要てこと？
        - tsc -> babel -> webpack の順にかけることが多い気がします。なんでと言われるとなんでだろ（from @cafedomancer）

:::info
梅本さんの回答: 
- The TypeScript Handbook に説明がありました。https://www.typescriptlang.org/docs/handbook/babel-with-typescript.html
一部を抜粋すると、
> A lot of the time the answer is “it depends”, or “someone may have decided for you” depending on the project. 

「多くの場合、その答えは場合による or 誰かが決めているかもしれません。」
>However, a useful heuristic could be:
    - Is your build output mostly the same as your source input files? Use tsc
    - Do you need a build pipeline with multiple potential outputs? Use babel for transpiling and tsc for type checking

しかし以下のような便利な経験則があります。
    - ビルド結果は元のソースコードとほとんど同じですか？ そうであれば tsc を使ってください。
    - 複数の出力を伴う可能性のあるビルドパイプラインが必要ですか？ そうであればトランスパイリングに babel を、型チェックに tsc を使ってください。
:::
- @yana-gi 
    - 式分の説明がよく理解できなかった :washimo: :onajiku:
        - “式文は、式のあとにセミコロンを書く文”
        - “関数呼び出しが式なのは、一般に関数呼び出しは返り値という結果を伴うから” ？
:::info
梅本さんの回答:
関数の戻り値がない (正確には戻り値が undefined である) 関数の呼び出しをしたいときに使うが式文なんじゃないでしょうか？ TypeScript の世界でいうと function の return type が void であるような関数です。このような関数は一般的には副作用を伴う  (副作用を期待して実行される)  ことが多いように思います。
![](https://i.imgur.com/RQu41n3.png)
:::
- @haruguchi-yuma 
    - 関数呼び出し以外の式文の例が知りたい！式文の理解のため

:::info
梅本さんの回答:
alert() なんかもそうだと思います。 
![](https://i.imgur.com/TPRznOb.png)
:::

### 各自の疑問点や気づき、学んだこと
- @mami-inuzuka
    - シグネチャ
        - {関数の名前, 引数の型, 引数の数, 戻り値の型} の組み合わせのこと
    - ECMAScript
        - ES2015以降毎年一回アップデートされる
      - プロポーザル
        - 一つの問題領域に対する新機能が1プロポーザル
        - ステージ1-4がある
          - ステージ3: TSで先行採用される
          - ステージ4: 正式採用
    - トランスパイル
        - あるプログラミング言語から、他のプログラミング言語に変換すること
        - TSの場合はJSに変換する
    - 型注釈の有無と型の有無は別物
        - 123という数値はnumber型を持っている
            - 下記のような変数宣言がある時、string型とnumber型を比較することになる
            - const target: string = 123;

- @yana-gi 
    - TypeScript→JavaScriptのトランスパイルは2段階
        - 型注釈を取り除く
        - 新しい構文を古い構文に変換する
    - TypeScript の言語のうち どこがJavaScript / TypeScript なのかを意識するとよい
    - enumやnamespace などのTypeScriptの独自機能は使うべきではない
    - （感想）TypeScript と JavaScript の関係がちょっとずつ分かってきた
    - 式分の説明がよく理解できなかった
        - “式文は、式のあとにセミコロンを書く文”
        - “関数呼び出しが式なのは、一般に関数呼び出しは返り値という結果を伴うから” ？
    - Rubyの変数名に絵文字が使えるのは知らなかった（JSは🙅‍♂️）

        ```❯ irb 
        irb(main):001:0> ✋ = 5
        => 5
        irb(main):002:0> ✋
        => 5
        ```

- @Maeda
	- トランスパイルはコンパイルの一種
	- 式と文
		- 式→値が入る
			- `1`, `'hello'`
		- 文→変数に代入できない（実行命令っぽい）
			- `const hoge = 1`
		- JSのif文は文（Rubyのif文は式）
	- JSでは絵文字は識別子として使えない（Rubyは使用可）
	- 型と型注釈は違うことに注意（Rubyにも型はある）

- @Saki
    - コンパイラの型チェックの所あとで読む! 
    - トランスパイルには2つある
        - 1. TypeScript→JavaScript(実際に本番環境でうごくコード)への変換
        - 2. 新しい構文を書いて→古い構文に変換してくれる
          - 新しい構文を使ってスマートに書きたいけど、古いブラウザ使ってるユーザーへの対応もしないといけない。良い所取り✨と思ったけれど、梅本さんのお話をお聞きしてると、何でも100%良い感じに変換してくれるわけでなさそう?
    - 「型がある」≠「型注釈がある」。たまに型注釈の有無のことを指してるのに型って言ってることがあるので注意。
        - Rubyには型はある/型注釈はない。
    - 文か式か見分けるポイント
      - **代入できるかどうか**。できれば式/できないなら文
      - JSではifは文なので代入できない/Rubyではifは式なので代入できる。(そういえば🍒本で代入したコードを見た)。言語によって式か文かも違う。
        - Rubyでのifは式：[プログラム・文・式 \(Ruby 3\.1 リファレンスマニュアル\)](https://docs.ruby-lang.org/ja/latest/doc/spec=2fprogram.html) 
      ```ruby
       hoge = if fuga == "piyo" #変数hogeに代入
         "Hello"
       else
         "World"
       end
      ```
      - 式文
        - 定義がよく分かってない。
        - `console.log("Hello");`でいうと、"Hello"を出力したいだけで、結果(戻り値のことぽい)に興味がない時に式文が便利

- @napple29 
    - トランスパイル
        - WebブラウザやNode.jsなどのJS処理系ではTSのままでは解釈できないためJSに変換する
        - 型注釈を取り除く・新しい構文を古い構文に変換する
    -　enumやnamespaceなどの独自機能は積極的に使うのは控えるべき 
    -　文と式は結果があるかどうかで見分ける
    -　変数宣言は文、if~も文
    -　変数に型注釈を与えられる `const 変数: 型 = 式;`
        -　型注釈で与えた型以外を代入するとエラー

- @paru871 
    - 「型がある」のと「型注釈がある」は別の話なので理解する際は混ざらないように気をつける！
    - 変数宣言の基本形の構文`const 変数名 = 式;`
    - 文と式は結果(返り値)の有無で区別する
    - 型注釈の書き方`const 変数: 型 = 式;`
    - 絵文字は識別子として使えるか？・・・JSは🙅‍♀️、Rubyは🙆‍♀️

- ＠haruguchi
    - トランスパイルもコンパイルの一種
    - babel考えた人は偉大だ！
    - ESYYYY　が2015年以降の正式名称
    - TypeScriptではステージ3になった時点で機能追加してるのでJSよりナウイ！
    - 文と式の区別がわかったようなわからないような
    - JSは変数名に絵文字は使えない
    - `const 変数名: 型 = 値`
    - そうか！関数呼び出しは値が返ってくるのでしきか！

- @SatoshiHaramura
    - TypeScriptコンパイラ
        - 型注釈で型チェックしている
        - トランスパイラ
            - 型注釈と取り除く
            - 新しい構文を古い構文に変換
    - 文と式の違いって
        - 文：結果(戻り値)が無い
        - 式：結果(戻り値)が有る
    - 型注釈
        - `変数名: 型`の`: 型`の部分

- @isshi-hasegawa
    - TSの独自機能は使わんで良い

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @mami-inuzuka
    - 前半で一旦わかったことなど書くの中だるみしなくて良い！

- @obregonia1 
    - 式と文の違いはよくわかってなかったが完全に理解した
    - JSでは識別子に絵文字が使えないことがわかったので誰かコントリビュートして下さい

- @yana-gi 
    - フィヨルド生と輪読会をするとRubyという共通の前提知識があるのが話やすくてよいな〜

- @haruguchi-yuma 
    - playground見ていてやっぱり実行前に怒られるの便利だと思った！
    - Paruさんおめでとうございます:tada: :tada:
    - このあとちょっとsakiさんの自作サービスタイムしますか！（お時間ある人で）
        - ありがとうございます！さらに就職しにくくなりましたー😹

- @napple29 
    - はるぐちさんリリースおめでとうございます！（出遅れた…） ありがとうございます:bow:
    - paruさんお誕生日🎂🎉 🍾

- @paru871 
    - playground、見やすいしJSの変換コードを見ると納得できるしエラーの出方が優しい感じで和みます。これから活用しよう！
    - 誕生日のお祝いメッセージ、ありがとうございます！引き続き楽しみながらやっていきたいと思います〜皆さまよろしくお願いします🙇‍♀️

- @Saki
    - 式と文のちがいは避けてきてたので今日わかってよかった 
    - 個人的には、前半と後半で気づきを書く場所は分けなくていいと思いました〜
    - haruguchiさんリリースおめでとうございます!!(昨日言えなかった)　:bow:
    - 自作サービスの進め方わからなくて五里霧中です...

- @Maeda
	- 式と文の違いが難しい。。。さらに式文が出てきてややこしいなってなってます

- @SatoshiHaramura
    - 前半と後半で分けることがよかったです！