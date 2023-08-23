---
emoji: 📝
title: JS 최빈값 Map 객체 활용
date: '2023-07-19 19:30:00'
author: DHyeonJ
tags: 내일배움캠프
categories: 내일배움캠프
---

# 기분에 따른 음식 추천

- 설문을 통해 가장 많이 나온 기분에 대한 음식을 추천해주기 위해서 최빈 값을 구한다.

## Js Map 객체

- ES6부터 새로 도입된 개념이다. 키와 값을 연결하기 위해 사용하는 데이터 유형이다. 프로토 타입은 `Object`.

  - 기존 객체와 달리 다양한 타입, 심지어 객체로도 키를 설정할 수 있다.
  - 객체와 달리 자료를 반복할 수 있어 `for-of`나 스프레드 연산자를 사용 가능하다.
  - 배열처럼 삽입된 순서나 크기를 구하기 쉽다.
  - 실행 시까지 키를 알 수 없고, 모든 키와 값들이 동일한 type일 경우 사용하기를 추천한다.

## 메서드

- `new Map()` : 일반 생성자 함수와 같이 변수처럼 사용 가능하다.
- `map.set(key, value)` : 객체와 비슷하게 키와 값을 한 번에 선언할 수 있다.
- `map.get(key)` : 객체와 비슷하게 인자에 키를 넣어 값이나 Undefined를 반환한다.
- `map.has(key)` : 데이터 존재 유무를 Boolean 값으로 반환한다.
- `map.delete(key)` : 키로 값을 제거한다.
- `map.clear()` : 모든 데이터를 삭제할 수 있다.
- `map.size` : 데이터 갯수를 반환한다.
- `map.keys()` : `iterable`키에 대해 반복 가능한 값을 반환한다.
- `map.values()` : `iterable` 값에 대해 반복 가능한 값을 반환한다.
- `map.entries`: `iterable`객체로 반환되며 각 값은 [key, value] 형태이다.
- `map.next()` : entries 메소드로 반환된 이터러블 객체 뒤에 활용돼 순차적으로 value, done 프로퍼트 제공.

## 코드에 적용해보기

// Map은 key와 value로 이루어진 자료구조.
// Map은 순서가 중요하지 않다.
// Map에서 key는 유일한 key를 가지고 있어야 한다.
// Map은 Obj와 비슷하다.

// const Array = [1 ,2, 3, 2,3, 2]

```js
const modeEmotion = (Array) => {
  let modeArr = new Map(); // modeArr :초 Map(0){} 기에 map자료 구조만 설정해줘서 빈 맵 자료 구조로 출력
  for (let n of Array) modeArr.set(n, (modeArr.get(n) || 0) + 1); // 변수 n이 배열만큼 for문 돌면서 ModeArr map구조에 set(N, (modeArr.get(N) || 0) +1)를 해준다...?)
// array[0]
modeArr.set(1, (false|| 0) +1) =>  modeArr.set(1,1) => {'1'=>'1'}
//array[1]  modeArr.set(1,1)
modeArr.set(2, (false || 0) +1) =>  modeArr.set(2,1) => {'1'=>'1', '2' => '1'} modeArr.get(2) 1 / get(1) 1
//array[2] modeArr.set(2,1) => {'1'=>'1', '2' => '1'} modeArr.get(2) 1 get(1) 1
modeArr.set(3, (false || 0) +1) => modeArr.get(3, 1) => {'1'=>'1', '2' => '1', '3'=>'1'}  modeArr.get(2) 1 / get(1) 1 / get(3) 1
//array[3]
modeArr.set(2, (1 || 0) + 1) => || 앞에 있을 때 false면 넘어간다.
modeArr.set(2, 2) => {'1'=>'1', '2' => '2', '3'=>'1' }   modeArr.get(2) 2 /  get(1) 1 / get(3) 1// 같은 경우에는 새로운 값으로 저장된다.
//array[4]

//array[5]


  modeArr = [...modeArr].sort((a, b) => b[1] - a[1]);
  return modeArr[0][0];
};
```

```toc

```

let modeArr = new Map()
console.log(modeArr); // Map(0){}

modeArr.set('1', '1')
console.log(modeArr); // Map(1) { '1' => '1' }

modeArr.set('react', '어려워요')
console.log(modeArr); // Map(2) { '1' => '1' , 'react' => '어려워요' }

modeArr.set('2', '1')
console.log(modeArr); // Map(2) { '1' => '1' , 'react' => '어려워요' , '2' => '1'}

modeArr.set('2', '1') // 중복될 경우에는 같은 것들이 합쳐져서 하나만 출력
console.log(modeArr); // Map(2) { '1' => '1' , 'react' => '어려워요' , '2' => '1'}

// 가져올 때
const result = modeArr.get(1)
console.log(result) // 1

const result2 = modeArr.get(2)
console.log(result2) // 1
