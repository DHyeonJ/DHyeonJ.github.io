---
emoji: 📝
title: JavaScript 1주차 quiz
date: '2023-05-23 19:30:00'
author: DHyeonJ
tags: 내일배움캠프
categories: 내일배움캠프
---

# 230523 내일배움캠프 2일차

✔️ 이번주부터 본격적으로 내일배움캠프가 시작되었다.
오늘 1주차 강의를 듣고 숙제로 간단한 알고리즘이 주어졌다.
처음이라 많이 낯설지만 배운거 복습한다고 생각하고 문제를 풀었다.

## Quiz1. 문자열 연습하기

<blockquote>

### 문제

- 대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다. 예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

### 제한 사항

- 문자열 s의 길이 : 50 이하의 자연수
</blockquote>

### 해결

- 대문자와 소문자 혼합되어 있는 것을 먼저 대문자로 통일시킨다.
- 반복문을 사용해 str에 'p'와 'y'이 있다면 카운트를 하고 그 값들을 비교해 같으면 true 다르면 False를 return한다.

### 작성답안

```js
function solution(s) {
  if (s.length > 50) {
    throw new Error('error');
  }

  // 1. 매개변수인 s를 대문자로 통일해야합니다.
  var str = s.toUpperCase();
  var count = 0;
  var count2 = 0;

  // 2. p,y의 갯수를 세야합니다.
  for (var i = 0; i < str.length; i++) {
    if (str[i] === 'P') {
      count++;
    }
    if (str[i] === 'Y') {
      count2++;
    }
  }
  // 3. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return
  // Tip : 수단보단 문제를 어떻게 풀지 로직을 적는것이 좋다
  if (count === count2) {
    return true; // return이 있으면 함수를 종료 눈에 보이지 않아도 함수안에는 리턴이 존재한다.
  } else {
    return false;
  }
}
const result = solution('pPoooyY'); // 인자
// const result = solution("Pyy")
console.log(result);
```

## Quiz2. 반복문, 조건문 연습하기

<blockquote>

### 문제

- 어떤 정수들이 있습니다. 이 정수들의 절댓값을 차례대로 담은 정수 배열 absolutes와 이 정수들의 부호를 차례대로 담은 불리언 배열 signs가 매개변수로 주어집니다. 실제 정수들의 합을 구하여 return 하도록 solution 함수를 완성해주세요.
</blockquote>

### 해결

- 반복문을 이용해 배열의 길이만큼 증가시켜 signs[i] 값이 참인지 거짓인지 조건문을 활용해 확인하고 그 해당 되는 값들을 answer에다 저장한 값들의 합을 구한다.

### 작성답안

````js
function solution(absolutes, signs) {
  // 1. 어떤 정수들이 있다.
  var answer = 0;

  // 2. 절대값을 담은 정수 배열과 부호를 담은 불리언 배열이 매개변수로 주어짐
  // 2-1. sings 길이와 absolutes길이가 같다
  for (var i = 0; i < absolutes.length; i++) {
    // 2-2. singis[i]가 참이면 absolutes[i] 양수
    if (signs[i] === true) {
      answer += absolutes[i];
      // 2-3. 아니면 음수를 의미
    } else if (signs[i] === false) {
      answer -= absolutes[i];
    }
  }

  return answer;
}

  // 3. 출력
  var absolutes = [4, 7, 12];
  var signs = [true, false, true];

  var result = solution(absolutes, signs);
  console.log(result);
  ```

````

```toc

```
