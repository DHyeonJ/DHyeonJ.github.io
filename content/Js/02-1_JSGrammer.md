---
emoji: 📝
title: JavaScript 기본 문법(2)
date: '2023-05-24 10:30:00'
author: DHyeonJ
tags: JS
categories: JS
---

## 3. 연산자

### (1) 더하기 연산자(+)

```js
console.log(1 + 1);
console.log(1 + '1');
```

### (2) 빼기 연산자(-)

```js
console.log(1 - '2'); // -1
console.log(1 - 2); // -1
```

### (3) 곱하기 연산자(\*)

```js
console.log(2 * 3); // 6
console.log('2' * 3); // 6
```

### (4) 나누기 연산자(/)

```js
console.log(4 / 2); // 2
console.log('4' / 2); // 2
```

### (5) 나머지 연산자(%)

```js
console.log(5 % 2); // 1
```

### (6) 할당 연산자(assignment)

#### (6-1) 등호 연산자(=)

```js
let x = 10;
console.log(x);
```

#### (6-2) 더하기 등호 연산자(+=)

```js
let x = 10;
x += 5;
console.log(x); // 15
```

#### (6-3) 빼기 등호 연산자(-=)

```js
let x = 10;
x -= 5;
// x = x - 5; // 위 코드랑 같은 의미이다.
console.log(x); // 5
```

#### (6-4) 곱하기 등호 연산자(\*)

```js
let a = 10;
a *= 2;
console.log(a); // 20
```

#### (6-5) 나누기 등호 연산자(/=)

```js
let x = 10;
x /= 5;
console.log(x); // 2
```

#### (6-6) 나머지 등호 연산자(%=)

```js
let x = 10;
x %= 5;
console.log(x); // 1
```

### (7) 비교 연산자(compatrson operators)

✔️ `true, false`를 반환하는 연산자

✔️ 일치 연산자를 배우기 전에 `= vs == vs === 차이`에 대해 먼저 알아보자!

```js
var a = 5; // 변수 a에 5를 저장한다.
5 == '5'; // 두 피연산자의 값의 타입이 다를 경우 자동으로 일부 피연산자의 타입을 변환 후 값을 비교합니다.
5 === 5; // 두 피연산자의 값이 타입까지 비교합니다.
```

#### (7-1) 일치 연산자(===) : 타입까지 일치해야 true를 반환하는 연산자

```js
console.log(2 === 2); // true
console.log('2' === 2); // false
console.log(2 === '2'); // false
```

#### (7-2) 불일치 연산자(!==) : 타입까지 일치해야 false를 반환하는 연산자

```js
console.log(2 !== 2); // false
console.log('2' !== 2); // true
console.log(2 !== '2'); // true
```

#### (7-3) 작다 연산자(<), 작거나 같다 연산자(<=)

```js
console.log(2 < 3); // true
console.log(2 <= 3); // true
console.log(3 <= 3); // true
console.log(4 <= 3); // false
```

#### (7-4) 크다 연산자(>), 크거나 같다 연산자(>=)

```js
console.log(2 > 3); // false
console.log(2 >= 3); // false
console.log(3 >= 3); // true
console.log(4 >= 3); // true
```

```toc

```
