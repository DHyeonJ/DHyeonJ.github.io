---
emoji: 📝
title: 프로그래머스
date: '2023-07-27 19:30:00'
author: DHyeonJ
tags: 내일배움캠프
categories: 내일배움캠프
---

# 프로그래머스

## 아이스아메리카노

### 문제

<blockquote>
머쓱이는 추운 날에도 아이스 아메리카노만 마십니다. 아이스 아메리카노는 한잔에 5,500원입니다. 머쓱이가 가지고 있는 돈 money가 매개변수로 주어질 때, 머쓱이가 최대로 마실 수 있는 아메리카노의 잔 수와 남는 돈을 순서대로 담은 배열을 return 하도록 solution 함수를 완성해보세요.
</blockquote>

### 해결 방안

- 배열 index 0번째에다가는 현재 가지고 있는 돈을 5500원으로 나눈 값의 몫만 저장하고,
  1번째 index에는 현재 가지고 있는 돈을 5500원으로 나눈 나머지 값을 저장해서 출력한다.

### 전체 코드

```js
function solution(money) {
  var answer = [];
  answer[0] = Math.floor(money / 5500);
  answer[1] = money % 5500;

  return answer;
}
```

```toc

```
