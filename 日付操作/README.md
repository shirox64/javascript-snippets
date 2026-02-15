# 日付操作

```js
/*
========================================
① 文字列 → 日付に変換
========================================
*/
// ISO形式（推奨）
const date1 = new Date("2026-02-15");
// 日時付き
const date2 = new Date("2026-02-15T10:30:00");

/*
========================================
② 日付 → 文字列に変換
========================================
*/
const now = new Date();
// ISO形式（UTC）
const isoString = now.toISOString();
// YYYY-MM-DD形式にする方法
const yyyyMMdd = now.toISOString().split("T")[0];

/*
========================================
③ 日付の比較
========================================
*/
const d1 = new Date("2026-02-10");
const d2 = new Date("2026-02-15");
// Dateは内部的にミリ秒なのでそのまま比較可能
const isBefore = d1 < d2; // true
const isAfter = d1 > d2; // false
// 完全一致チェック（ミリ秒比較）
const isSame = d1.getTime() === d2.getTime();

/*
========================================
④ 何日差があるか
========================================
*/
// 差分はミリ秒で取得される
const diffMs = d2 - d1;
// 1日 = 1000ms * 60秒 * 60分 * 24時間
const diffDays = diffMs / (1000 * 60 * 60 * 24);
// 小数を処理する場合
const diffDaysFloor = Math.floor(diffDays); // 切り捨て
const diffDaysCeil = Math.ceil(diffDays); // 切り上げ

/*
========================================
⑤ 日付の加算・減算
========================================
*/
const baseDate = new Date("2026-02-15");
// 7日後
baseDate.setDate(baseDate.getDate() + 7);
// 1ヶ月後
baseDate.setMonth(baseDate.getMonth() + 1);
// 1年前
baseDate.setFullYear(baseDate.getFullYear() - 1);

/*
========================================
⑥ よく使う取得メソッド
========================================
*/
const sample = new Date();
const year = sample.getFullYear(); // 年
const month = sample.getMonth(); // 月（0〜11）⚠️注意
const day = sample.getDate(); // 日
const weekDay = sample.getDay(); // 曜日（0=日曜）
const hours = sample.getHours(); // 時
const minutes = sample.getMinutes(); // 分
const seconds = sample.getSeconds(); // 秒

/*
========================================
⑦ 今日の日付を取得
========================================
*/
const today = new Date();

/*
========================================
⑧ 実務でよくあるチェック処理
========================================
*/
// 今日より過去か判定
const inputDate = new Date("2026-02-10");
if (inputDate < new Date()) {
  console.log("過去の日付です");
}

// 有効期限チェック
const expireDate = new Date("2026-03-01");
if (new Date() > expireDate) {
  console.log("期限切れ");
}

/*
========================================
⑨ タイムゾーン注意ポイント
========================================
*/
// toISOString() はUTCになる
const utc = new Date().toISOString();
// ローカル時間で表示したい場合
const localString = new Date().toLocaleString();

/*
========================================
まとめ
========================================
・文字列からは ISO形式で生成するのが安全
・日付同士はそのまま比較できる
・差分はミリ秒なので 1000*60*60*24 で割る
・getMonth() は 0始まりに注意
・タイムゾーン問題に気をつける
*/
```
