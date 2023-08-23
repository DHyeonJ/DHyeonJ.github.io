---
emoji: 📝
title: 프로그래머스
date: '2023-07-28 19:30:00'
author: DHyeonJ
tags: 내일배움캠프
categories: 내일배움캠프
---

# 프로그래머스

## 머쓱이보다 키 큰 사람

### 문제

<blockquote>
머쓱이는 학교에서 키 순으로 줄을 설 때 몇 번째로 서야 하는지 궁금해졌습니다. 머쓱이네 반 친구들의 키가 담긴 정수 배열 array와 머쓱이의 키 height가 매개변수로 주어질 때, 머쓱이보다 키 큰 사람 수를 return 하도록 solution 함수를 완성해보세요.
</blockquote>

### 해결 방안

- filter함수를 통해 배열의 값과 머쓱이의 키를 비교해 머쓱이 보다 큰 사람의 개수를 변수에 담아 출력한다.

### 전체 코드

```js
function solution(array, height) {
  const friend = array.filter((item) => item > height);
  return friend.length;
}
```

```toc

```
