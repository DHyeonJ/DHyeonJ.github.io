---
emoji: 📝
title: React 입문(Component, JSX)
date: '2023-06-13 19:30:00'
author: DHyeonJ
tags: 내일배움캠프
categories: 내일배움캠프
---

## Component

### React Component란?

<blockquote>
컴포넌트를 통해 UI를 재사용이 가능한 `개별적인 여러 조각`으로 나누고, 각 조각을 개별적으로 살펴볼 수 있다.
개념적으로 컴포넌트는 `JavaScript 함수`와 유사하다.
"props"라고 하는 임의의 `입력`을 받은 후, `화면에 어떻게 표시`되는지를 기술하는 `React 엘리먼트를 반환`한다.
</blockquote>

### React 컴포넌트를 표현하는 두 가지 방법

1. 함수형 컴포넌트

```js
// props라는 입력을 받음
// 화면에 어떻게 표현되는지를 기술하는 React 엘리먼트를 반환

function welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

// 쉬운 표현으로 변경하면 아래와 같다.
function App() {
  return <div>hello</div>;
}
```

2. 클래스형 컴포넌트

```js
class welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

### Component 보는 방법

- 코드를 볼 때는 영역을 나누어서 보면 조금 더 편하다.
- 컴포넌트 밖에서는 내가 필요한 파일을 import하거나, 또는 export default라는 기능을 통해 내가 만든 컴포넌트를 밖으로 내보내는 코드가 있다.
- 컴포넌트 안에서는 자바스크립트를 쓸 수 있는 부분이 있다.
- retur을 기준으로 아래부분에서는 Jsx(=HTML)을 작성할 수 있다. `작성된 HTML 코드와 값들이 화면에 보여진다.`

## JSX

### JSX란?

- `JavaScript + XML`로 Js안에 HTML 태그를 사용할 수 있다.
- JSX문법을 사용해서 React 요소를 만들고 DOM에 렌더링 시켜서 그린다.

### JSX 실습

1. 태그는 꼭 닫아야한다.

   ```js
   function App() {
     return (
       <div className="App">
         <input type="text" />
       </div>
     );
   }
   ```

2. 무조건 1개의 엘리먼트를 반환하기

   ```js
   function App () {
       return (
        <p>안녕하세요! 리액트입니다.</p>
        <input type="text" />
       );
   }
   ```

3. JSX에서 javascript를 사용하려면

   ```js
   function App() {
     const cat_name = 'perl';
     return <div>hello {cat_name}!</div>;
   }
   ```

4. Class 대신 className

- JSX로 작성하는 태그 내에서 클래스 명을 정해줄 땐 속성 값을 className으로 사용한다.

  ```js
  <div className="App">
  ```

5. 인라인으로 style주기

- css문법 대신 json 형식으로 작성하면 된다.

```html
<p style="color: orange; font-size: 20px;">orange</p>
```

```jsx
<p style={{ color: 'orange', fontSize: '20px' }}>orange</p>;

// 스타일 객체를 변수로 만들고 사용이 가능하다.
function App() {
  const styles = {
    color: 'orange',
    fontSize: '20px',
  };
  return (
    <div className="App">
      <p style={styles}>orange</p>
    </div>
  );
}
```

```toc

```
