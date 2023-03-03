# 🐔 React Element

type과 props를 가지는 React의 객체

React 라이브러리에 있는 React.createElement(...)를 이용하여 만들 수 있으며 type으로 HTML 태그 이름을 가지고 그 이외의 특징을 props로 관리하는 객체 형태로 정의된다.

```jsx
// createElement를 이용해서 React Element 만들기
React.createElement(
  'div',
  { className: 'name' },
  'React'
)
```

```jsx
// createElement를 이용해서 만들어진 React Element 객체
{
  type: 'div',
  props: {
    className: 'name',
    children: 'React'
  }
}
```

## React Component

props를 받아서, React Element를 반환하는 함수 혹은 클래스

React Element Tree를 캡슐화한다.
