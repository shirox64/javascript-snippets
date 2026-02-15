# ループ処理

## for

基本的なループ。回数が決まっているときに使います。

```js
for (let i = 0; i < 5; i++) {
  console.log(i);
}
// 0 1 2 3 4
```

## for...of

配列や文字列など イテラブル なものを簡単に回すときに使う。

```js
const arr = ["a", "b", "c"];
for (const item of arr) {
  console.log(item);
}
// a b c
```

## for...in

オブジェクトの プロパティ名 をループするときに使う。

```js
const obj = { name: "Alice", age: 25 };
for (const key in obj) {
  console.log(key, obj[key]);
}
// name Alice
// age 25
```

## 配列メソッドを使ったループ

```js
const arr = [1, 2, 3, 4, 5];

// forEach（副作用用）
arr.forEach((num) => console.log(num));

// map（変換用）
const doubled = arr.map((num) => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]

// filter（条件で抽出）
const even = arr.filter((num) => num % 2 === 0);
console.log(even); // [2, 4]

// reduce（集計）
const sum = arr.reduce((acc, num) => acc + num, 0);
console.log(sum); // 15
```
