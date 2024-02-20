---
emoji: 🧑‍💻
title: flag에 따라 다른 값 반환하기
date: '2024-02-06 23:00:00'
author: DHyeonJ
tags: JS 프로그래머스 코딩테스트 입문
categories: algorithm
---

## 문제

두 정수 `a`, `b`와 boolean 변수 `flag`가 매개변수로 주어질 때, `flag`가 true면 `a` + `b`를 false면 `a` - `b`를 return 하는 solution 함수를 작성해 주세요.

## 제한사항

- -1,000 ≤ `a`, `b` ≤ 1,000

## 입출력 예

| a   | b   | flag  | result |
| --- | --- | ----- | ------ |
| -4  | 7   | true  | 3      |
| -4  | 7   | false | -11    |

## 입출력 예 설명

`입출력 예 #1`

- 예제 1번에서 flag가 true이므로 a + b = (-4) + 7 = 3을 return 합니다.

`입출력 예 #2`

- 예제 2번에서 flag가 false이므로 a - b = (-4) - 7 = -11을 return 합니다.

## 코드

```js
const solution = (a, b, flag) => (flag ? a + b : a - b);
```

<br>

<blockquote>
💡 Tip : 함수식에서 return문과 {} 사이에 아무 것도 없다면 <font color="red">모두 생략이 가능</font>하며, <font color="red">{}는 ()로 변형</font>이 된다.
</blockquote>

## 코드 해설

- flag 값이 참이면 a+b 값을 반환한다.
- flag 값이 거짓이면 a-b 값을 반환한다.

```toc

```
