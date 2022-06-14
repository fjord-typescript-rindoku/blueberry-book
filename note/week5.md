# 【第5週】ブルーベリー本輪読会🫐🫐<br />(2022-06-11)

[![hackmd-github-sync-badge](https://hackmd.io/fE1fYRIDR0auZCXNSHEasA/badge)](https://hackmd.io/fE1fYRIDR0auZCXNSHEasA)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）
- [playground](https://www.typescriptlang.org/play)

---
## 2022-06-11（土）
### タイムスケジュール
- 雑談(5min) ~9:05
- 輪読(40min) ~9:45
- 前半の記入(5min) ~9:50
- 休憩(10min) ~10:00
- 輪読(45min) 前半での疑問の解消含む ~10:45
- まとめ(15min) ~ 11:00 （「わからなかったこと疑問」→「気づき」→「振り返り」の順で）

### 進行係

- 前半
    - @satoshiharamura
- 後半
    - @Saki

### ドライバー

- 前半
    - @cafedomancer
- 後半
    - @mae-da 

### 読んだところ

- p.53 「コラム5」 から p.75 「3.1.1 オブジェクトは “ 連想配列 ” である」　まで

### 次回

- p.75 「3.1.2 オブジェクトリテラル(1)基本的な構文」 から

### 自由に使う共有スペース

### わからなかったこと・疑問など

-

- 

- 
  	
### 各自の疑問点や気づき、学んだこと

- @Saki
    - for文だと`i++`でも`++i`でも変わらない理由がわかった
    - !を使うと、`!!"123" //=>true` というように真偽値に変換できる。でも`!`を2つ使うと人が読みづらいコードになりそうな印象。
    - `&&`と`||`はRubyと同じ挙動
    - `??=`は、左辺がnullかundefinedの場合右辺を返し、それ以外なら左辺を返す
    - `変数 = 変数 || 式`と`変数 ||= 式`の違い
        - 戻り値は違うが過程が違うと解釈した
        - `変数 = 変数 || 式`の場合は、左辺に当てはまったら、変数を変数に代入するが(つまり同じ値)、`変数 ||= 式`の場合は、変数にすでにtruthyな値が入ってたら代入しない

- @cafedomancer
    - `NaN !== NaN`
    - `!` 演算子の優先順位をちゃんと考えたことはなかった :face_with_rolling_eyes: 
    - `||` より `??` のほうが安全そうな気がした
    - JavaScript のオブジェクトは連想配列！
        - Ruby だと Hash
        - Java だと Map
        - Python だと dictionary
        - 配列も連想配列？ php とかやると理解が深まるかも
            ```php
            array("foo" => "bar", "bar" => "foo");
            array("foo", "bar", "hello", "world");
            ```

- @haruguchi-yumawo
    - NaNはnumber型
    - NaNは何と比較してもfalse
    - `&&`や`||`の短絡評価はRubyと同じだった
        - `&&`Reactでよく出てくるイメージ
    - `||=` `&&=` `??=`はES2021で比較的新しい構文だった
    - セミコロンつけない派だったんですが、なんかつけてたら楽しくなってきたので今はつけてます！
        - JavaScript Standard Style のルールがセミコロンをつけないようになっていますね (not ESLint?)
            - ESLintじゃないのか、その中の特定のルールってことですか！
                - ESLint に怒られるのは JavaScript Standard Style の ESLint プラグインを設定しているからですかね。ESLint のデフォルトの設定ではセミコロンはつけるようになっているようです。 https://eslint.org/docs/2.0.0/rules/semi#always

- @yanagi
    - オペランドにNaNが与えられた時は常にfalseを返す
        - xがNaNだったら`x < 100` も `x === NaN`もfalseを返すので罠
    - `&&`や`||` の戻り値（短絡評価）はRubyと同じ
    - Null合体演算子 `??=`
        - 右辺がnull か undefined の場合に右辺の値を返す
        - [Null 合体演算子 \(??\) \- JavaScript \| MDN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator)
    -  `&&=・||=・??=` は必要がなければ代入すらされない（代入しても値が同じなので）
    - TypeScriptではオブジェクトは大事な概念
    - TypeScriptではオブジェクトの出番が多くクラスはほぼ全く使われない
        - VueとかReact とかのフレームワークも確かにほとんどクラスを使わない
        - サーバーサイドだとどうなんだろう？


- @mae-da 
	- `const x = NaN`
	- `x === NaN`は`false`になる
	- Boolean(式)と!!式は同じ挙動
	- `変数　||= 式`は`変数 || (変数 = 式)`と同じ。（≠`変数 = 変数 || 式`）
	- `;`が必要な部分と省略して良い部分を理解できてるなら省略しても良い
	- [Null 合体演算子 (??) - JavaScript | MDN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator)

- @SatoshiHaramura
    - フォント(Fira Codeなど)によっては、リガチャー(合字)がある！
        - 合字（ごうじ、英: Ligature;リガチャー）とは、複数の文字を合成して一文字にしたもの
        - ![](https://i.imgur.com/1mNFhcx.png)
    - `x === NaN`はfalseになる
    - `Number.isNaN(NaN)`はtrueになる
    - `||=`は、左辺が`falsy`のとき、右辺を返す
        - `変数 || (変数 = '何か')`を行っている！
    - `??=`は、左辺が`null`または`undefined`のとき、右辺を返す

- @SummerTree 
    - Playgroundで無限ループするとこわれる
    - (参考)配列と連想配列は内部構造がかなり違います。操作の計算量とかも（多分）違います。
        - PHPは謎すぎます（配列と連想配列の区別がない）
        - 配列と連想配列はアクセスのされ方が結構異なりますからね〜
            - yes
    - 連想配列 ≒ ハッシュ(テーブル) ≒ マップ ≒ 辞書(dictionary)


### 本日の振り返り(よかった点・次回に向けての改善点等)

- @Saki
    - 疑問点の共有ありがとうございます〜🙏
    	- 🙏 :bow:
    - いつも輪読会の運営色々考えてくださっててありがとうございます〜

- @isshi-hasegawa
    - わがままを言ったら2章飛ばす流れになった😜
        - だれかが「2 章は JS の復習ですけど読むんですか？」的なことを前に言っていたのを聞いたので、飛ばしてよかったんじゃないかなーと思います

- @SummerTree 
    - 念願のベリー本輪読会に（途中からですが）参加できたので嬉しいです！さっき本買いました！
        - ワイワイ
        - :medetai!::waiwaiwaiwai::tada:

- @haruguchi
    - やり方色々変えてすみません:pray:
        - 他にも意見あったら教えてくださいー！！！
        - 参加者の意向を臨機応変にくみとっていただいてありがとうございます〜🙏
    - 早く型の話したいですよね！笑
    - MaedaさんがTS plarygroundを破壊してて楽しかった？
    - データ構造勉強したいかも！

- @yanagi
    - Playgroundが壊せて楽しかった
    

- @SatoshiHaramura
    - 冒頭に、先週の疑問点を深堀りしてくださって、復習&学びになりました！ありがとうございます！

- @obregonia1 
    - 2章飛ばしてくれてありがたい🙏

- @mae-da 
	- 梅本さんはなんでも知ってて怖い（フォントのところ）
	    - ふぉんとですね… :cop:
	- 来週休みます🙏

- @cafedomancer 
    - Fira Code オススメですよ！:oo!: :naruhodo:
