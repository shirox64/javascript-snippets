# データの型変換

## Number() と parseInt() の違い（比較表）

| 比較項目             | Number()                | parseInt()                           |
| -------------------- | ----------------------- | ------------------------------------ |
| 文字列全体が数値必要 | ✅ 必要                 | ❌ 不要（途中までOK）                |
| 小数                 | そのまま変換            | 切り捨て（整数のみ）                 |
| 空文字 `""`          | 0                       | NaN                                  |
| 途中に文字           | NaN                     | 途中まで変換（例: `"123abc"` → 123） |
| 先頭が文字           | NaN                     | NaN                                  |
| Boolean変換          | 可能（true→1, false→0） | 不可                                 |
| 進数指定             | 不可                    | 可能（第2引数で指定）                |
| 厳密さ               | 厳密                    | やや緩い                             |

## Number()

```js
Number("123"); // 123
Number("123.45"); // 123.45
Number("123abc"); // NaN
Number(""); // 0
Number(true); // 1
Number(false); // 0
```

## parseInt()

```js
parseInt("123"); // 123
parseInt("123.45"); // 123
parseInt("123abc"); // 123
parseInt("abc123"); // NaN
parseInt("10", 2); // 2（2進数）
parseInt("100", 10); // 100
```

## parseFloat()

```js
parseFloat("123.45"); // 123.45
parseFloat("123.45px"); // 123.45
```
