---
emoji: 📝
title: JavaScript 2주차 quiz
date: '2023-05-24 19:30:00'
author: DHyeonJ
tags: 내일배움캠프
categories: 내일배움캠프
---

# 230523 내일배움캠프 3일차

✔️ 이번주부터 본격적으로 내일배움캠프가 시작되었다.
오늘 2주차 강의를 듣고 숙제로 간단한 알고리즘이 주어졌다.
오늘도 새로운 도전을 해보려고한다.

## Quiz. 문자열 연습하기

<blockquote>

### 문제

- 문자열로 구성된 리스트 strings와, 정수 n이 주어졌을 때, 각 문자열의 인덱스 n번째 글자를 기준으로 오름차순 정렬하려 합니다. 예를 들어 strings가 ["sun", "bed", "car"]이고 n이 1이면 각 단어의 인덱스 1의 문자 "u", "e", "a"로 strings를 정렬합니다.

### 제한 사항

- strings는 길이 1 이상, 50이하인 배열입니다.
- strings의 원소는 소문자 알파벳으로 이루어져 있습니다.
- strings의 원소는 길이 1 이상, 100이하인 문자열입니다.
- 모든 strings의 원소의 길이는 n보다 큽니다.
- 인덱스 1의 문자가 같은 문자열이 여럿 일 경우, 사전순으로 앞선 문자열이 앞쪽에 위치합니다.
</blockquote>

### 해결

- 문자열 앞에 인덱스에 해당하는 문자를 붙인다.
- 해당 배열을 사전순으로 `sort`이용해 오름차순 정렬한다.
- 정렬된 배열의 가장 앞 글자를 `replace`이용해 제거한다.

### 작성답안

```js
function solution(strings, n) {
  var arr = [];
  // 1. 문자열 앞에 인덱스에 해당하는 문자를 붙인다
  for (var i = 0; i < strings.length; i++) {
    // string[0][1]글자를 가져와서 strings[i]번째 변수 앞에 붙인 정보를 다시 strings[i]에 저장한다.
    strings[i] = strings[i][n] + strings[i];
  }
  // 2. 해당 배열을 사전순으로 오름차순 정렬
  strings.sort();

  // 3. 정렬된 배열의 가장 앞 글자를 제거
  for (var j = 0; j < strings.length; j++) {
    strings[j] = strings[j].replace(strings[j][0], '');
    arr.push(strings[j]);
  }

  return arr;
}

console.log(solution(['sun', 'bed', 'car'], 1));
```

## 느낀점

- 무작정 코드부터 작성하는것이 아니라 문제를 읽을 수 있는 능력부터 키워야한다는 것을 느낀 하루였다.

```toc

```
