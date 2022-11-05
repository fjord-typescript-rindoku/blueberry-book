# 【第20週】ブルーベリー本輪読会🫐🫐<br />(2022-11-05)

[![hackmd-github-sync-badge](https://hackmd.io/TY87YL1DTQurxw6mRgJSvg/badge)](https://hackmd.io/TY87YL1DTQurxw6mRgJSvg)


###### tags: `ブルーベリー本`

- [開催概要](https://hackmd.io/1kCgi6_tSGukG0KZrqDLvA)
- [ブルーベリー本輪読会ノートまとめ](https://hackmd.io/Ih6bdReuR3eQpYkGaCx8pg)
- [プロを目指す人のためのTypeScript入門-サポートページ](https://gihyo.jp/book/2022/978-4-297-12747-3/support)（正誤表・サンプルコードのダウンロードページ）

---
## 2022-11-05（土）

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

- p.216 「5.3.4 privateとprotectedの動作と使いどころ」 から

### 次回

### 自由に使う共有スペース

```javascript=
// haruguchiさん作成filter関数
function filter(array, cb) {
  const result = []
   for (const a of array) {
     if (cb(a)) { result.push(a) };
   }
  return result
}
```

```typescript=
class User {
    name: string;
    #age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.#age = age
    }

    public isAdult(): boolean {
        return this.#age >= 20;
    }

    public filterOlder(users: readonly User[]): User[] {
        return users.filter( function(u) { return  u.#age > this.#age});
    }
}

const uhyo = new User("uhyo", 25);
const john = new User("John Smith", 15);
const bob = new User("Bob", 40);

const older = uhyo.filterOlder([john, bob]);
console.log(older); //=> エラー
```

- filter関数で使用されているコールバック関数はharuguchiさんが作ったfilter関数の実装をみると、メソッド呼び出しされていなく、関数呼び出し
- thisがundefinedであることがわかる（strictmodeでのトップレベルのthisはundefined）

### わからなかったこと・疑問など

### 各自の疑問点や気づき、学んだこと

- @Maeda8 
	- thisはusestrictモードでは`undefined`, ブラウザでは`window`, nodeでは`globalThis`
	- protectedは子クラス側で指定したプロパティの値を書き換えられることに注意
	- implementsキーワードを使うと、そのクラスのインスタンス雨は与えられた肩の部分型であるということになる。
		- implementsを使うことでクラスの実装を明確にできる。（型チェックしたい箇所が明確になる。欲しいプロパティ、メソッドが明確になる）
	- メソッド内の実装を見ればthisが何かわかる。面倒だけど・・

- @haruguchi
    - implementsキーワードを使うとどんなプロパティを持っていて欲しいかという情報が担保させる。
    - 意図せずそのプロパティの消したり、型を変更してしまった場合に気づけて便利

### 本日の振り返り(よかった点・次回に向けての改善点等)

- @haruguchi-yuma 
    - Ruby Silver楽しい
    - JS楽しい！

- @Maeda8 
	- filterメソッドの内部実装がこうなってるんじゃないか？をすらすら書いていたharuguchiさんすごくないか？
