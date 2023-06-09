# [JS] PRO 181851 전국대회 선발 고사

[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/181851)

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

처음에는 for문을 돌려서 참석여부에 따라 조건을 세우고 참석한 학생만 배열에 담아 인덱스번호로 비교해주려고 했지만 실패했다.

두번째 방법으로 생각했던게 어처피 반복문을 돌려서 배열에 넣어줄 것이라면 map을 쓰고 필터링을 하면 되지 않을까 생각을 했고 푸는과정에서 해당하는 등수의 학생 인덱스 값을 알아야했다.

따라서 그냥 el만 넣는게 아니라 그에 해당하는 인덱스 값도 배열에 같이 넣어줘야한다. 그리고 오름차순으로 정렬 후, 해당하는 인덱스값에 따라 결과를 반환해주면 된다.

<!-- ```옆에 사용하는 언어를 기입하세요 e.g. javascript, python -->

```javascript
function solution(rank, attendance) {
  const rankArray = rank
    .map((el, i) => [el, i])
    .filter((el, i) => attendance[i] === true)
    .sort((a, b) => a[0] - b[0]);

  return 10000 * rankArray[0][1] + 100 * rankArray[1][1] + rankArray[2][1];
}
```

## 소요시간

1시간 좀 넘은 것 같습니다.

## 어려웠던 점

그냥 반복문 안에서 true인 친구들만 뽑아서 인덱스를 구하고 새로운 배열에 넣어서 앞에 3개만 뽑으려고 했는데 문제 이해를 잘못했다.

## 배운 점

map과 filter에서도 인덱스를 이용할 수 있다는 점을 다시 복기할 수 있었다. 이 문제는 기억했다가 다시 풀어봐야 할 것 같다.

## 궁금한 점

더 효율적이게 풀 수 있으면 알려주세용!🙇‍♀️
