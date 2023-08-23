---
emoji: 📝
title: React 입문(필수문법, CRA)
date: '2023-06-12 19:30:00'
author: DHyeonJ
tags: 내일배움캠프
categories: 내일배움캠프
---

## 필수문법

### 상수와 변수

- ES6로 넘어오면서 var키워드 보단 const, let 변수를 많이 사용하게 됩니다.
- cosnt vs let : 둘 다 block level scope({})를 가진다.
  - const : 재할당이 안되고 내부 속성값은 수정 가능하다.
  - let : 재할당이 가능하다.

### Object 선언, 단축 속성, 객체 복사

#### 객체를 선언 하는 방법

```js
// 선언 방법
cosnt person = {
    name: '홍길동',
    age: 21,
    company : 'hongildong',
    doSomething: () => {},
}

```

#### 생략해서 표현하는 방법

```js
const name = '르탄';
const age = 21;

// 단축 속성 : key-value가 일치하면 생략한다.

// 변경 전
cosnt person = {
    name: '홍길동',
    age: 21,
    company : 'hongildong',
    doSomething: () => {},
}

// 변경 후
const person = {
    name,
    age,
    company: 'hongildong',
    doSomething: function(){},
}
```

### 얕은 복사

```js
const obj1 = { value1: 10 };
const obj2 = obj1; // 얕은 복사
const obj3 = JSON.parse(Json.stringify(obj1));

obj1.value1 += 1;

// 결과를 예상해보세요!
console.log('obj1', obj1); //  {value1: 11}
console.log('obj2', obj2); //  {value1: 11}
console.log('obj3', obj3); //  {value1: 10}
```

### Template Literals

```js
// 일반 텍스트
`string text` // 멀티라인
`string text line 1
string text line 2` // 플레이스 홀더를 이용한 표현식
`string text ${expressiong} string text`;
```

### 배열/객체 비구조화 (Array/Object Destructuring)

- `구조분해 할당`이라고도 한다.

#### 객체의 비구조화(구조분해 할당)

```js
// person 객체 안에 있는 값들이 구조가 해제되어 각각 변수에 할당됩니다.
const person = {
    name: '홍길동'
    age: 21
}

const { name, age } = person;
console.log(`$(name)님, $(age)살이시네요!`);
```

#### 배열의 비구조화(구조분해 할당)

```js
const testArr = [1, 2, 3, 4, 5];
const [val1, val2, val3, val4, val5] = testArr;

console.log(val1);

// 추가 예제
let [name] = ['Tom', 10, 'Seoul'];
// let [, age] = ["Tom", 10, "Seoul"];
// let [name, age, region] = ["Tom", 10, "Seoul"];
// let [name, age, region, height] = ["Tom", 10, "Seoul"];
// let [name, age, region, height = 150] = ["Tom", 10, "Seoul"];
```

### 전개 연산자(Spread Operator)

```js
// Case 1

let [name, ...rest] = ['Tom', 10, 'Seoul'];

// Case 2

let names = ['Steve', 'John'];
let students = ['Tom', ...names, ...names];

// Case 3

let tom = {
  name: 'Tom',
  age: 10,
  region: 'Seoul',
};

let steve = {
  ...tom,
  name: 'Steve',
};
```

### Arrow Function

- ES6에서 자주 사용되는 문법 중에 하나로 `화살표 함수`라고도 불린다.

```js
const mysum1 = (x, y) => x + y;
const mysum2 = (x, y) => {x, y};
const mysum3 = (x, y) => ({x: x, y: y});
const mysum4 = (x, y) => {
    return {x: x, y: y};
}
const mysum5 = function(x, y) {
    return {x: x, y: y};
}
const mysum6(x, y) {
    return {x: x, y: y};
}
```

## CRA

### CRA란?

- 한 줄의 명령어 입력으로 React 프로젝트 개발에 필수요소를 자동으로 구성하는 방법이다.

### CRA로 프로젝트 생성하기

#### 명령어

- ls : 현재 내가 위치하고 있는 폴더의 하위 폴더들을 볼 수 있다.
- cd : 내가 이동하고 싶은 폴더로 이동할 수 있다.

```bash
yarn create react-app test
```

### CRA로 생성한 프로젝트 실행하기

```bash
cd test # test 폴더로 이동
yarn start # 프로젝트 시작
```

### 상대경로 import -> 절대경로 지정하기

- jsconfig.json 파일을 만든다. (단, root경로에 생성해야한다.)

- 아래의 코드를 작성한다.

```js
    {
        "compilerOption": {
            "baseUrl" : "src"
        },
        "include" : ["src"]
    }

```

```toc

```
