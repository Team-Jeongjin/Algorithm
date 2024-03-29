# [JS] BOJ 11727/2xn 타일링2

[문제 링크](https://www.acmicpc.net/problem/11727)

<!-- 제목으로 다음과 같은 내용으로 작성해주세요 ! -->
<!-- 📕 백준 : BOJ 문제번호/문제제목 e.g. BOJ 2577/숫자의 개수 -->
<!-- 📗 프로그래머스 : PRO 문제번호/문제제목 e.g. PRO 120812/최빈값 구하기 -->
<!-- 백준허브를 사용하시면 프로그래머스의 문제번호도 확인하실 수 있습니다 -->

## Table of Contents

- [✍🏻 풀이](#풀이)
- [⏰ 소요시간](#소요시간)
- [🫠 어려웠던 점](#어려웠던-점)
- [😮 배운 점](#배운-점)
- [🤔 궁금한 점](#궁금한-점)

## 풀이

<!-- ```옆에 사용하는 언어를 기입하세요 e.g. javascript, python -->

```javascript
const readline = require("readline");
const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

const input = [];
rl.on("line", function (line) {
  input.push(line);
}).on("close", function () {
  solution();
  process.exit();
});

function solution() {
  const n = Number(input[0]);
  const memo = Array.from({length: 1001}, _ => 0);
  console.log(topDown(memo, n));
}

// d[n] = 2 * d[n - 2] + d[n - 1];
function topDown(memo, n) {
  if (memo[n] > 0) {
    return memo[n];
  }
  if (n === 1) {
    return memo[1] = 1;
  }
  if (n === 2) {
    return memo[2] = 3;
  }
  memo[n] = topDown(memo, n - 1) % 10007 + 2 * topDown(memo, n - 2) % 10007;
  return memo[n] % 10007;
}
```
## 소요시간
15분 

## 어려웠던 점

## 배운 점

## 궁금한 점

