# 文字列操作

```js
/*
========================================
① 文字列の基本
========================================
*/
const str = "Hello, World!";
// 文字列の長さ
console.log(str.length); // 13
// インデックスで取得
console.log(str[0]); // "H"
console.log(str.charAt(0)); // "H"
/*
※ JavaScriptの文字列はイミュータブル（変更不可）
str[0] = "h" は無効
*/

/*
========================================
② 文字列の結合
========================================
*/
// +演算子で結合
const name = "Alice";
const greeting = "Hello, " + name + "!";
console.log(greeting); // "Hello, Alice!"
// テンプレートリテラル（推奨）
const greeting2 = `Hello, ${name}!`;
console.log(greeting2); // "Hello, Alice!"

/*
========================================
③ 大文字・小文字変換
========================================
*/
const text = "JavaScript";
console.log(text.toUpperCase()); // "JAVASCRIPT"
console.log(text.toLowerCase()); // "javascript"

/*
========================================
④ 文字列の検索
========================================
*/
const sentence = "I love JavaScript";
// 部分文字列が含まれるか
console.log(sentence.includes("Java")); // true
// 文字列の位置を取得（先頭から）
console.log(sentence.indexOf("Java")); // 7
// 文字列の位置を取得（後ろから）
console.log(sentence.lastIndexOf("a")); // 12

/*
========================================
⑤ 文字列の切り出し
========================================
*/
const str2 = "Hello, World!";
// substring(start, end) → endは含まれない
console.log(str2.substring(0, 5)); // "Hello"
// slice(start, end)
console.log(str2.slice(7, 12)); // "World"
// 負の値で末尾から指定
console.log(str2.slice(-6, -1)); // "World"

/*
========================================
⑥ 文字列の置換
========================================
*/
const text2 = "I like cats";
// 1つだけ置換
console.log(text2.replace("cats", "dogs")); // "I like dogs"
// 全部置換（正規表現 /g 必須）
console.log(text2.replace(/c/g, "d")); // "I like dads"

/*
========================================
⑦ 文字列の分割・結合
========================================
*/
const csv = "apple,banana,cherry";
// 分割
const fruits = csv.split(",");
console.log(fruits); // ["apple","banana","cherry"]
// 配列を文字列に結合
const joined = fruits.join(" | ");
console.log(joined); // "apple | banana | cherry"

/*
========================================
⑧ トリム（前後の空白削除）
========================================*/
const input = "   hello world   ";
console.log(input.trim()); // "hello world"
console.log(input.trimStart()); // "hello world   "
console.log(input.trimEnd()); // "   hello world"

/*
========================================
⑨ 文字列の繰り返し
========================================*/
const repeatStr = "ha".repeat(3);
console.log(repeatStr); // "hahaha"

/*
========================================
⑩ 文字列の比較
========================================*/
const a = "abc";
const b = "ABC";
console.log(a === b); // false
console.log(a.toLowerCase() === b.toLowerCase()); // true

/*
========================================
⑪ 実務でよく使うパターン
========================================*/
// 1. 入力値の前後空白削除
const username = "   Alice   ";
const cleanName = username.trim();

// 2. 部分一致チェック
const query = "JS";
const isFound = sentence.includes(query);

// 3. CSV文字列の配列化
const csvInput = "1,2,3,4";
const array = csvInput.split(",");

// 4. テンプレートリテラルで文字列組み立て
const item = "Apple";
const msg = `I like ${item}`;

// 5. 文字列の置換（複数）
const text3 = "red, green, red";
const newText = text3.replace(/red/g, "blue");
```
