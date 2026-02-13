# 数学関数(Math)

## 丸め処理

```js
// 四捨五入 round()
console.log(Math.round(3.5)); // 4
// 切り捨て floor()
console.log(Math.floor(3.9)); // 3
// 切り上げ ceil()
console.log(Math.ceil(3.1)); // 4
```

## 最大最小

```js
// 最大 max()
Math.max(10, 20, 5); // 20
// 最小 min()
Math.min(10, 20, 5); // 5

// 一般的な使い方
const numbers = [10, 20, 5];
console.log(Math.max(...numbers)); // 20
```

## べき乗・平方根

```js
console.log(Math.pow(2, 3)); // 8
console.log(Math.sqrt(16)); // 4
```

## 絶対値

```js
console.log(Math.abs(-10)); // 10
```

## ランダム数

```js
console.log(Math.random()); // 0以上1未満の乱数
```
