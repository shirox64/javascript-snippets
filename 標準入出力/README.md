# 標準入出力

## readlineを使った標準入力

```js
process.stdin.resume();
process.stdin.setEncoding("utf8");

const lines = [];
const reader = require("readline").createInterface({
  // 標準入力から読み込み
  input: process.stdin,
  // 出力先を標準出力にする
  // コンソールに入力内容が表示されるので確認時に使用
  // output: process.stdout,
});

// 1行入力されるたびに呼ばれる処理
reader.on("line", (line) => {
  lines.push(line);
});

// 入力が終わったら呼び出される処理
reader.on("close", () => {
  const N = lines[0];
  for (let i = 0; i < N; i++) {
    const line = lines[i + 1].split(" ");
    console.log("hello = " + line[0] + ", world = " + line[1]);
  }
});
```

## readFileSyncを使った標準入力

```js
const fs = require("fs");

const STDIN_FD = 0;
const lines = fs.readFileSync(STDIN_FD, "utf8").split("\n");
// "/dev/stdin"だとWindowsで動かないので注意
// const lines = fs.readFileSync("/dev/stdin", "utf8").split("\n");

const N = lines[0];
for (let i = 0; i < N; i++) {
  const line = lines[i + 1].split(" ");
  console.log("hello = " + line[0] + ", world = " + line[1]);
}
```

## ファイルの実行コマンド

Linux / Windows コマンドプロンプト

```sh
node app.js < input.txt
```

Windows PowerShell

```PowerShell
Get-Content input.txt | node app.js
```
