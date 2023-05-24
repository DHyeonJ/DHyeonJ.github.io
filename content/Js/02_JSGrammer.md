---
emoji: 📝
title: JavaScript 기본 문법(1)
date: '2023-05-24 09:10:00'
author: DHyeonJ
tags: JS
categories: JS
---

## 1. 변수와 상수

✔️ 변수 : 메모리에 저장하고, 저장한 값을 읽어들여서 재사용합니다.

### (1) 변수 5가지 주요 개념

1️⃣ 변수 이름 : 저장된 값의 고유 이름

2️⃣ 변수 값 : 변수에 저장된 값

3️⃣ 변수 할당 : 변수에 값을 저장하는 행위

4️⃣ 변수 선언 : 변수를 사용하기 위해 컴퓨터에 알리는 행위

5️⃣ 변수 참조 : 변수에 할당된 값을 읽어오는 것

### (2) 변수 let vs var vs const 차이

1️⃣ let : 같은 이름으로 재선언이 불가능하며 재할당 가능

```js
let myLet = 'Hello World1';
let myLet = 'Test 2'; // 재선언이 불가능
myLet = 'GoodBye 1'; // 재할당은 가능
console.log(myLet);
```

2️⃣ var : 같은 이름으로 재선언, 재할당 가능

```js
var myVar = 'Hello World';
var myVar = 'Test 1'; // 재선언 가능
myVar = 'GoodBye'; // 재할당 가능
console.log(myVar);
```

3️⃣ const : 같은 이름으로 재선언, 재할당이 불가능

```js
const myConst = 'Hello World2';
const myConst = 'Test 3'; // 재선언 불가능
myConst = 'GoodBye 2'; // 재할당 불가능
console.log(myConst);
```

## 2. 데이터 타입과 형 변환

✔️ 코드를 작성할 때 데이터 타입을 작성하지 않고, 실제 코드가 터미널에서 실행 될 때 데이터 타입이 결정된다.

### (1) 데이터 타입

#### 1. 숫자(Number)

- 1-1 정수(Integer)

```js
let num1 = 10;
console.log(num1);
console.log(typeof num1);
```

<br>

- 1-2 실수(Float)

```js
let num2 = '3.14';
console.log(num2);
console.log(typeof num2);
```

<br>

- 1.3 지수형(Exp)

```js
let num3 = 2.5e5; // 2.5 * 10^5
console.log(num3);
console.log(typeof num3);
```

<br>

- 1.4 NaN(Not a Number)

```js
let num4 = 'Hello' / 2;
console.log(num4);
```

<br>

- 1-5. Infinity(양의 무한대)

```js
let num5 = 1 / 0;
console.log(num5);
console.log(typeof num5);
```

<br>

- 1-6. Infinity(음의 무한대)

```js
let num6 = -1 / 0;
console.log(num6);
console.log(typeof num6);
```

#### 2. 문자열(String)

✔️ 문자 : string(문자열 = 문자의 나열)

```js
let str = 'Hello World';
console.log(str); // str문자를 출력
console.log(typeof str); // str문자의 타입을 출력
```

<br>

- 2-1. 문자열 길이(length) 확인하기

```js
console.log(str.length);
```

<br>

- 2-2. 문자열 결합(concatenation)

```js
let str1 = 'Hello, ';
let str2 = 'world!';
let result = str.concat(str2);
console.log(result);
```

<br>

- 2-3. 문자열 자르기(substr, slice)

```js
let str3 = 'Hello, World';
console.log(str3.substr(7, 5)); // 시작 위치부터 몇 개까지 자를건지 지정
console.log(str3.slice(7, 12)); // 시작 위치부터 끝 위치까지 지정
```

<br>

- 2-4. 문자열 검색(search)

```js
let str4 = 'Hello, World1';
console.log(str4.search('World')); // world가 시작된 지점
```

<br>

- 2-5. 문자열 대체(replace)

```js
let str5 = 'Hello, World1';
let result01 = str5.replace('World', 'Javascript');
console.log(result01);
```

<br>

- 2-6. 문자열 분할(split)

```js
let str6 = 'apple, banana, kiwi';
let result02 = str6.split(',');
console.log(result02);
```

#### 3. 불리언(Boolean)

✔️ true(참), false(거짓)

```js
let bool1 = true;
let bool2 = false;

console.log(bool1);
console.log(typeof bool1);
console.log(bool2);
console.log(typeof bool2);
```

#### 4. undefined(un : not, define : 정의하다.)

```js
let x;
console.log(x);
```

#### 5. null : 값이 존재하지 않음을 '명시적'으로 나타내는 방법 `null = undefined`

```js
let y = null;
console.log(y);
```

#### 6. 객체(Object) : key-value pair

```js
let person = {
  name: 'choi',
  age: 20,
  isMarried: true,
};

console.log(typeof person);
```

#### 7. 배열(Array) : 여러 개의 데이터를 순서대로 저장하는 데이터 타입!!!

```js
let number = [1, 2, 3, 4, 5];
let fruits = ['apple', 'banana', 'orange'];
```

### (2) 형 변환

✔️ 형 변환 : 타입을 다른 타입으로 변환하는 의미를 가지고 있다.

#### 1. 암시적 형 변환

- 1-1. 문자열 변환

```js
let result1 = 1 + '2';
console.log(result1); // 12
console.log(typeof result1); // string

let result2 = '1' + true;
console.log(result2); // 1true
console.log(typeof result2); // string

// {}, null, undefined + "1" => 문자열
```

<br>

- 1-2. 숫자 변환

```js
let result3 = 1 - '2';
console.log(result3); // -1
console.log(typeof result3); // number

let result4 = '2' * '3';
console.log(result4); // 6
console.log(typeof result4); // number
```

<br>

- 1-3. Boolean 변환

```js
console.log(Boolean(0));
console.log(Boolean(''));
console.log(Boolean(null));
console.log(Boolean(undefined));
console.log(Boolean(NaN));
console.log('------------------');
console.log(Boolean('false'));
console.log(Boolean({}));
```

#### 2. 명시적 형 변환

- 2-1. 문자열 변환

```js
let result5 = String(123);
console.log(typeof result5);
console.log(result5);

let result6 = String(true);
console.log(typeof result6);
console.log(result6);

let result7 = String(false);
console.log(typeof result7);
console.log(result7);

let result8 = String(null);
console.log(typeof result8);
console.log(result8);

let result9 = String(undefined);
console.log(typeof result9);
console.log(result9);
```

<br>

- 2-2. 숫자 변환

```js
let result10 = Number('123');
console.log(result10);
console.log(typeof result10);
```

```toc

```
