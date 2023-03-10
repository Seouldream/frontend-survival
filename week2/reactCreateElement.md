# ๐ React.createElement

ํธ์ถ์ ๊ธฐ๋ณธ ํํ๋ ์๋์ ๊ฐ์ React.createElement(component, props, ...children)

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

### ๋งค๊ฐ๋ณ์

type: ํ์์ ๋ฐ๋์ ์ ์ํ ๋ฆฌ์กํธ ์ปดํฌ๋ํธ ํ์์ด์ด์ผ ํ๋ค. ์๋ฅผ ๋ค๋ฉด ์ด๊ฒ์ 'div'๋ 'span'๊ณผ ๊ฐ์ ํ๊ทธ ์ด๋ฆ์ด ๋  ์๋ ์๊ณ  ํน์ ํจ์๋ ํด๋์ค ํ๋๊ทธ๋จผํธ์ ๊ฐ์ ํน๋ณํ ๋ฆฌ์กํธ ์ปดํฌ๋ํธ์ผ ์ ์๋ค.

props: ์์ฑ๊ฐ์ ๋ฐ๋์ ๊ฐ์ฒด์ด๊ฑฐ๋ null์ด์ด์ผํ๋ค. null์ ์๋ ฅํ๋ฉด ํ๋์ ๋น ๊ฐ์ฒด์ ๊ฐ์ด ๋ค๋ฃจ์ด์ง๋ค. ๋ฆฌ์กํธ๋ ์ฌ์ฉ์๊ฐ ์๋ ฅํ ์์ฑ๊ณผ ์ผ์นํ๋ ์์ฑ์ ๊ฐ์ง ์์๋ฅผ ์์ฑํ๋ค.

Note that ref and key from your props object are special and will not be available as element.props.ref and element.props.key on the returned element. They will be available as element.ref and element.key.

optional ...children: Zero or more child nodes. They can be any React nodes, including React elements, strings, numbers, portals, empty nodes (null, undefined, true, and false), and arrays of React nodes.

### Returns

createElement returns a React element object with a few properties:

type: The type you have passed. props: The props you have passed except for ref and key. If the type is a component with legacy type.defaultProps, then any missing or undefined props will get the values from type.defaultProps. ref: The ref you have passed. If missing, null. key: The key you have passed, coerced to a string. If missing, null. Usually, youโll return the element from your component or make it a child of another element. Although you may read the elementโs properties, itโs best to treat every element as opaque after itโs created, and only render it.

## JSX์์ด ์์๋ง๋ค๊ธฐ

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

๊ฐ์ jsx ์ฝ๋

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
