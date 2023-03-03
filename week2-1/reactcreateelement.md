# 🐔 React.createElement

호출의 기본 형태는 아래와 같음 React.createElement(component, props, ...children)

```javascript
const element = createElement(type, props, ...children)
```

```jsx
import { createElement } from 'react';

function Greeting({ name }) {
  return createElement(
    'h1',
    { className: 'greeting' },
    'Hello'
  );
}
```

### 매개변수

type: 타입은 반드시 유요한 리액트 컴포넌트 타입이어야 한다. 예를 들면 이것은 'div'나 'span'과 같은 태그 이름이 될 수도 있고 혹은 함수나 클래스 프래그먼트와 같은 특별한 리액트 컴포넌트일 수 있다.

props: 속성값은 반드시 객체이거나 null이어야한다. null을 입력하면 하나의 빈 객체와 같이 다루어진다. 리액트는 사용자가 입력한 속성과 일치하는 속성을 가진 요소를 생성한다.

Note that ref and key from your props object are special and will not be available as element.props.ref and element.props.key on the returned element. They will be available as element.ref and element.key.

optional ...children: Zero or more child nodes. They can be any React nodes, including React elements, strings, numbers, portals, empty nodes (null, undefined, true, and false), and arrays of React nodes.

### Returns

createElement returns a React element object with a few properties:

type: The type you have passed. props: The props you have passed except for ref and key. If the type is a component with legacy type.defaultProps, then any missing or undefined props will get the values from type.defaultProps. ref: The ref you have passed. If missing, null. key: The key you have passed, coerced to a string. If missing, null. Usually, you’ll return the element from your component or make it a child of another element. Although you may read the element’s properties, it’s best to treat every element as opaque after it’s created, and only render it.

## JSX없이 요소만들기

```jsx
import { createElement } from 'react';

function Greeting({ name }) {
  return createElement(
    'h1',
    { className: 'greeting' },
    'Hello ',
    createElement('i', null, name),
    '. Welcome!'
  );
}
```

같은 jsx 코드

```jsx
function Greeting({ name }) {
  return (
    <h1 className="greeting">
      Hello <i>{name}</i>. Welcome!
    </h1>
  );
}
```

```jsx
export default function App() {
  return createElement(Greeting, { name: 'Taylor' });
}
```

```jsx
export default function App() {
  return <Greeting name="Taylor" />;
}
```
