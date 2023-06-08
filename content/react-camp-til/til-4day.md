---
emoji: 📝
title: JavaScript 3주차 quiz
date: '2023-05-25 19:30:00'
author: DHyeonJ
tags: 일일회고
categories: 회고
---

## Quiz1. 나이든 유저

<blockquote>

### 문제

- 가장 아래의 코드가 실행 되었을 때, “Passed ~” 가 출력되도록 getAge 함수를 채워주세요

</blockquote>

### 생각해보기

- 새로운 나이 값을 어떻게하면 저장할까?
- user1, user2를 다르게 해서 둘이 같지 않다고 증명할까?

### 해결

- 새로운 객체(result), 변수(prop)를 선언한다.
- 반복문을 통해 user 객체를 살펴본 후, result 객체에 똑같은 정보를 저장한다.
- result.age값과 agedUser에 있는 인자 6를 passesTime에 넘긴 값을 저장하고 다시 result.age에 저장한다.
- 조건문을 통해 user2와 user1이 같은지 비교한다.

### 작성답안

```js
var user = {
  name: 'john',
  age: 20,
};

var getAged = function (user, passedTime) {
  var result = {};
  for (var prop in user) {
    result[prop] = user[prop];
  }
  result.age += passedTime;
  return result;
};

var agedUser = getAged(user, 6);

var agedUserMustBeDifferentFromUser = function (user1, user2) {
  if (!user2) {
    console.log("Failed! user2 doesn't exist!");
  } else if (user1 !== user2) {
    console.log('Passed! If you become older, you will be different from you in the past!');
  } else {
    console.log('Failed! User same with past one');
  }
};

agedUserMustBeDifferentFromUser(user, agedUser);
```

### 출력 결과

```console
Passed! If you become older, you will be different from you in the past!
```

<hr>

## Quiz2. 어떤 매치가 성사될까?

<blockquote>

### 문제

- 출력의 결과를 제출해주세요, 그리고 그 이유를 최대한 상세히 설명해주세요
- 주의사항 : 브라우저에서 테스트해주세요(Chrome → 개발자 도구 → 콘솔에 입력하여 실행)
</blockquote>

### 생각해보기

- `객체, 함수의 this 바인딩 개념`과 `클로저`의 개념을 이해해야한다.

### 작성답안

```js
var fullname = 'Ciryl Gane';

var fighter = {
  fullname: 'John Jones',
  opponent: {
    fullname: 'Francis Ngannou',
    getFullname: function () {
      // 1. 객체 this 바인딩 : Francis Ngannou
      return this.fullname;
    },
  },

  getName: function () {
    // 2. 객체 this 바인딩 : John Jones
    return this.fullname;
  },

  // 화살표 함수는 this 바인딩을 안하기 때문에 var fullname = "Ciryl Gane"; 값을 가져온다.
  getFirstName: () => {
    // 3. 함수 this 바인딩 : Ciryl
    return this.fullname.split(' ')[0];
  },

  // 함수 호출부()가 없으면 스스로 선언하고 호출한다. 즉시실행함수
  getLastName: (function () {
    // 4. 함수 this 바인딩 : Gane
    return this.fullname.split(' ')[1];
  })(),
};

console.log('Not', fighter.opponent.getFullname(), 'VS', fighter.getName());
console.log('It is', fighter.getName(), 'VS', fighter.getFirstName(), fighter.getLastName);
```

### 출력 결과

```console
Not Francis Ngannou VS John Jones
It is John Jones VS Ciryl Gane
```

## 느낀점

아직 문제를 이해하는 능력이나 전반적인 실력이 많이 부족하다고 느꼈다. 중요한 것은 포기하지 않는 마음이라고 생각한다.
앞으로 계속 나아가다보면 더 좋은 미래가 기다리고있다고 항상 생각하면서 공부에 임해야겠다고 생각이 들었다.

```toc

```
