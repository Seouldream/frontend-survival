# ๐ React StrictMode

StrictMode๋ ์ ํ๋ฆฌ์ผ์ด์ ๋ด์ ์ ์ฌ์ ์ธ ๋ฌธ์ ๋ฅผ ์์๋ด๊ธฐ ์ํ ๋๊ตฌ์๋๋ค. Fragment์ ๊ฐ์ด UI๋ฅผ ๋ ๋๋งํ์ง ์์ผ๋ฉฐ, ์์๋ค์ ๋ํ ๋ถ๊ฐ์ ์ธ ๊ฒ์ฌ์ ๊ฒฝ๊ณ ๋ฅผ ํ์ฑํํฉ๋๋ค.

Strict ๋ชจ๋๋ ๊ฐ๋ฐ ๋ชจ๋์์๋ง ํ์ฑํ๋๊ธฐ ๋๋ฌธ์, ํ๋ก๋์ ๋น๋์๋ ์ํฅ์ ๋ผ์น์ง ์์ต๋๋ค.

์ ํ๋ฆฌ์ผ์ด์ ๋ด ์ด๋์๋ ์ง ์๋์ ๊ฐ์ด strict ๋ชจ๋๋ฅผ ํ์ฑํํ  ์ ์์ต๋๋ค.

```jsx
import React from 'react';

function ExampleApplication() {
  return (
    <div>
      <Header />
      <React.StrictMode>
        <div>
          <ComponentOne />
          <ComponentTwo />
        </div>
      </React.StrictMode>
      <Footer />
    </div>
  );
}
```

์์ ์์์์, Header์ Footer ์ปดํฌ๋ํธ๋ Strict ๋ชจ๋ ๊ฒ์ฌ๊ฐ ์ด๋ฃจ์ด์ง์ง ์์ต๋๋ค. ํ์ง๋ง, ComponentOne๊ณผ ComponentTwo๋ ๊ฐ๊ฐ์ ์์๊น์ง ๊ฒ์ฌ๊ฐ ์ด๋ฃจ์ด์ง๋๋ค.

StrictMode๋ ์๋์ ๊ฐ์ ๋ถ๋ถ์์ ๋์์ด ๋ฉ๋๋ค.

* ์์ ํ์ง ์์ ์๋ช์ฃผ๊ธฐ๋ฅผ ์ฌ์ฉํ๋ ์ปดํฌ๋ํธ ๋ฐ๊ฒฌ
* ๋ ๊ฑฐ์ ๋ฌธ์์ด ref ์ฌ์ฉ์ ๋ํ ๊ฒฝ๊ณ 
* ๊ถ์ฅ๋์ง ์๋ findDOMNode ์ฌ์ฉ์ ๋ํ ๊ฒฝ๊ณ 
* ์์์น ๋ชปํ ๋ถ์์ฉ ๊ฒ์ฌ
* ๋ ๊ฑฐ์ context API ๊ฒ์ฌ
* Ensuring reusable state

## ์์ ํ์ง ์์ ์๋ช์ฃผ๊ธฐ๋ฅผ ์ฌ์ฉํ๋ ์ปดํฌ๋ํธ ๋ฐ๊ฒฌ

๋ธ๋ก๊ทธ ๊ธ์์ ์ค๋ชํ์๋ฏ, ๋น๋๊ธฐ React ์ ํ๋ฆฌ์ผ์ด์์์ ํน์  ์๋ช์ฃผ๊ธฐ ๋ฉ์๋๋ค์ ์์ ํ์ง ์์ต๋๋ค. ํ์ง๋ง ์ ํ๋ฆฌ์ผ์ด์์ด ์๋ ํํฐ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ฌ์ฉํ๋ค๋ฉด, ํด๋น ์๋ช์ฃผ๊ธฐ ๋ฉ์๋๊ฐ ์ฌ์ฉ๋์ง ์๋๋ค๊ณ  ์ฅ๋ดํ๊ธฐ ์ด๋ ต์ต๋๋ค. Strict ๋ชจ๋๋ ์ด๋ฌํ ๊ฒฝ์ฐ์ ๋์์ด ๋ฉ๋๋ค!

Strict ๋ชจ๋๊ฐ ํ์ฑํ๋๋ฉด, React๋ ์์ ํ์ง ์์ ์๋ช์ฃผ๊ธฐ ๋ฉ์๋๋ฅผ ์ฌ์ฉํ๋ ๋ชจ๋  ํด๋์ค ์ปดํฌ๋ํธ ๋ชฉ๋ก์ ์ ๋ฆฌํด ๋ค์๊ณผ ๊ฐ์ด ์ปดํฌ๋ํธ์ ๋ํ ์ ๋ณด๊ฐ ๋ด๊ธด ๊ฒฝ๊ณ  ๋ก๊ทธ๋ฅผ ์ถ๋ ฅํฉ๋๋ค.

strict mode unsafe lifecycles warning Strict ๋ชจ๋์ ์ํด ๋ฐ๊ฒฌ๋ ๋ฌธ์ ๋ค์ ํด๊ฒฐํ๋ค๋ฉด, ํฅํ ๋ฆด๋ฆฌ์ฆ๋๋ React์์ concurrent ๋ ๋๋ง์ ์ด์ ์ ์ป์ ์ ์์ ๊ฒ์๋๋ค.

## ๋ ๊ฑฐ์ ๋ฌธ์์ด ref ์ฌ์ฉ์ ๋ํ ๊ฒฝ๊ณ 

์ด์ ์ React์์ ๋ ๊ฑฐ์ ๋ฌธ์์ด ref API์ ์ฝ๋ฐฑ API๋ผ๋, ref๋ฅผ ๊ด๋ฆฌํ๋ ๋ ๊ฐ์ง ๋ฐฉ๋ฒ์ ์ ๊ณตํ์์ต๋๋ค. ๋ฌธ์์ด ref๊ฐ ์ฌ์ฉํ๊ธฐ ๋ ํธ๋ฆฌํ์ง๋ง ๋ช๋ช ๋จ์ ๋ค์ด ์์์ต๋๋ค. ๊ทธ๋์ ๊ณต์์ ์ผ๋ก๋ ์ฝ๋ฐฑ ํํ๋ฅผ ์ฌ์ฉํ๋ ๊ฒ์ ๊ถ์ฅํ์์ต๋๋ค.

React 16.3์์๋ ์ฌ๋ฌ ๋จ์  ์์ด ๋ฌธ์์ด ref์ ํธ๋ฆฌํจ์ ์ ๊ณตํ๋ ์ธ ๋ฒ์งธ ๋ฐฉ๋ฒ์ ์ถ๊ฐํ์์ต๋๋ค.

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);

    this.inputRef = React.createRef();
  }

  render() {
    return <input type="text" ref={this.inputRef} />;
  }

  componentDidMount() {
    this.inputRef.current.focus();
  }
}
```

์ด์ ๋ ๊ฐ์ฒด ref๊ฐ ๋ฌธ์์ด ref๋ฅผ ๊ต์ฒดํ๋ ์ฉ๋๋ก ๋๋ฆฌ ๋ํด์ก๊ธฐ ๋๋ฌธ์, Strict ๋ชจ๋๋ ๋ฌธ์์ด ref์ ์ฌ์ฉ์ ๋ํด ๊ฒฝ๊ณ ํฉ๋๋ค.

์ฃผ์

```plain-text
์ฝ๋ฐฑ ref๋ ์๋ก์ด createRef API์ ๋ณ๊ฐ๋ก ์ง์ํด์ ์ง์๋  ์์ ์๋๋ค.

์ปดํฌ๋ํธ์ ์ฝ๋ฐฑ ref๋ฅผ ๊ต์ฒดํ  ํ์๋ ์์ต๋๋ค. ์ฝ๋ฐฑ ref๋ ์กฐ๊ธ ๋ ์ ์ฐํ๊ธฐ ๋๋ฌธ์, ๊ณ ๊ธ ๊ธฐ๋ฅ์ผ๋ก์ ๊ณ์ ์ง์ํ  ์์ ์๋๋ค.
```

createRef API์ ๋ํด์ ์์๋ณด๊ธฐ

## ๊ถ์ฅ๋์ง ์๋ findDOMNode ์ฌ์ฉ์ ๋ํ ๊ฒฝ๊ณ 

์ด์ ์ React์์ ์ฃผ์ด์ง ํด๋์ค ์ธ์คํด์ค๋ฅผ ๋ฐํ์ผ๋ก ํธ๋ฆฌ๋ฅผ ํ์ํด DOM ๋ธ๋๋ฅผ ์ฐพ์ ์ ์๋ findDOMNode๋ฅผ ์ง์ํ์์ต๋๋ค. DOM ๋ธ๋์ ๋ฐ๋ก ref๋ฅผ ์ง์ ํ  ์ ์๊ธฐ ๋๋ฌธ์ ๋ณดํต์ ํ์ํ์ง ์์ต๋๋ค.

findDOMNode๋ ํด๋์ค ์ปดํฌ๋ํธ์์๋ ์ฌ์ฉํ  ์ ์์์ง๋ง, ๋ถ๋ชจ๊ฐ ํน์  ์์์ด ๋ ๋๋ง๋๋ ๊ฒ์ ์๊ตฌํ๋ ์ํฉ์ด ํ์ฉ๋์ด, ์ถ์ํ ๋ ๋ฒจ์ด ๋ฌด๋์ง๊ฒ ๋์์ต๋๋ค. ์ด๋ก ์ธํด ๋ถ๋ชจ๊ฐ ์์์ DOM ๋ธ๋์๊น์ง ๋ฟ์ ๊ฐ๋ฅ์ฑ์ด ์์ด ์ปดํฌ๋ํธ์ ์ธ์ธํ ๊ตฌํ์ ๋ณ๊ฒฝํ  ์ ์๊ฒ ๋์ด ๋ฆฌํฉํ ๋ง์ด ์ด๋ ค์์ง๋ ์ํฉ์ ๋ง๋ค๊ณ  ๋ง์์ต๋๋ค. findDOMNode๋ ํญ์ ์ฒซ ๋ฒ์งธ ์์์ ๋ฐํํ์ง๋ง, Fragment์ ํจ๊ป ์ฌ์ฉํ  ๊ฒฝ์ฐ ์ปดํฌ๋ํธ์์ ์ฌ๋ฌ DOM ๋ธ๋๋ฅผ ๋ ๋๋งํ๊ฒ ๋ฉ๋๋ค. findDOMNode๋ ์ผํ์ฑ, ์ฝ๊ธฐ ์ ์ฉ API์๋๋ค. ๋ฌผ์ด๋ณด์์ ๋๋ง ๊ฐ์ ๋ฐํํฉ๋๋ค. ์์ ์ปดํฌ๋ํธ๊ฐ ๋ค๋ฅธ ๋ธ๋๋ฅผ ๋ ๋๋งํ  ๊ฒฝ์ฐ, ๋ณ๊ฒฝ ์ฌํญ์ ๋์ํ  ๋ฐฉ๋ฒ์ด ์์ต๋๋ค. ๊ทธ๋ฌ๋ฏ๋ก, findDOMNode๋ ํญ์ ๋ณํ์ง ์๋, ๋จ์ผ DOM ๋ธ๋๋ฅผ ๋ฐํํ๋ ์ปดํฌ๋ํธ์์๋ง ์ ์์ ์ผ๋ก ์๋ํด์์ต๋๋ค.

ref๋ฅผ ๋๊ฒจ์ฃผ๋ ๋ฐฉ์์ ์ฌ์ฉํด ์ปค์คํ ์ปดํฌ๋ํธ์ ref๋ฅผ ๋๊ฒจ DOM๊น์ง ๋ฟ๊ฒ ํ๋ ๊ฒ์ผ๋ก, ์ด๋ฅผ ๋ถ๋ชํ๊ฒ ๋ง๋ค ์ ์์ต๋๋ค.

DOM ๋ธ๋๋ฅผ ๊ฐ์ธ๋ ๋ํผ๋ฅผ ๋ง๋ค์ด ref๋ฅผ ๋ฐ๋ก ๋ถ์ด๋ ๊ฒ ์ญ์ ๊ฐ๋ฅํฉ๋๋ค.

class MyComponent extends React.Component { constructor(props) { super(props); this.wrapper = React.createRef(); } render() { return

{this.props.children}; } }

```plain-text
์ฃผ์

๋ธ๋๊ฐ ๋ ์ด์์ ๋ฐ๊นฅ์ ์์๊ฐ ๋๋ ๊ฒ์ ๋ง๊ณ ์ ํ๋ค๋ฉด, CSS์์ display: contents ์์ฑ์ ์ฌ์ฉํ  ์ ์์ต๋๋ค.
```

## ์์์น ๋ชปํ ๋ถ์์ฉ ๊ฒ์ฌ

๊ฐ๋์ ์ผ๋ก React๋ ๋ ๋จ๊ณ๋ก ๋์ํฉ๋๋ค.

๋ ๋๋ง ๋จ๊ณ๋ ํน์  ํ๊ฒฝ(์๋ฅผ ๋ค์ด, DOM๊ณผ ๊ฐ์ด)์ ์ด๋ค ๋ณํ๊ฐ ํ์ํ ์ง ๊ฒฐ์ ํ๋ ๋จ๊ณ์๋๋ค. ์ด ๊ณผ์ ์์ React๋ render๋ฅผ ํธ์ถํ์ฌ ์ด์  ๋ ๋์ ๊ฒฐ๊ณผ๊ฐ์ ๋น๊ตํฉ๋๋ค. ์ปค๋ฐ ๋จ๊ณ๋ React๊ฐ ๋ณ๊ฒฝ ์ฌํญ์ ๋ฐ์ํ๋ ๋จ๊ณ์๋๋ค(React DOM์ ๊ฒฝ์ฐ React๊ฐ DOM ๋ธ๋๋ฅผ ์ถ๊ฐ, ๋ณ๊ฒฝ ๋ฐ ์ ๊ฑฐํ๋ ๋จ๊ณ๋ฅผ ๋งํฉ๋๋ค). ์ด ๋จ๊ณ์์ React๋ componentDidMount ๋ componentDidUpdate ์ ๊ฐ์ ์๋ช์ฃผ๊ธฐ ๋ฉ์๋๋ฅผ ํธ์ถํฉ๋๋ค. ์ปค๋ฐ ๋จ๊ณ๋ ์ผ๋ฐ์ ์ผ๋ก ๋งค์ฐ ๋น ๋ฅด์ง๋ง, ๋ ๋๋ง ๋จ๊ณ๋ ๋๋ฆด ์ ์์ต๋๋ค. ์ด๋ก ์ธํด, ๊ณง ์ถ๊ฐ๋  concurrent ๋ชจ๋(์์ง ๊ธฐ๋ณธ์ ์ผ๋ก๋ ๋นํ์ฑํ๋จ)๋ ๋ ๋๋ง ์์์ ๋ ์์ ๋จ์๋ก ๋๋๊ณ , ์์์ ์ค์งํ๋ค ์ฌ๊ฐํ๋ ๋ฐฉ์์ผ๋ก ๋ธ๋ผ์ฐ์ ๊ฐ ๋ฉ์ถ๋ ๊ฒ์ ํผํฉ๋๋ค. ์ฆ, React๋ ์ปค๋ฐํ๊ธฐ ์ ์ ๋ ๋๋ง ๋จ๊ณ์ ์๋ช์ฃผ๊ธฐ ๋ฉ์๋๋ฅผ ์ฌ๋ฌ ๋ฒ ํธ์ถํ๊ฑฐ๋ ์์ ์ปค๋ฐ์ ํ์ง ์์ ์๋(์๋ฌ ํน์ ์ฐ์ ์์์ ๋ฐ๋ฅธ ์์ ์ค๋จ) ์์ต๋๋ค.

๋ ๋๋ง ๋จ๊ณ ์๋ช์ฃผ๊ธฐ ๋ฉ์๋๋ ํด๋์ค ์ปดํฌ๋ํธ์ ๋ฉ์๋๋ฅผ ํฌํจํด ๋ค์๊ณผ ๊ฐ์ต๋๋ค.

* constructor
* componentWillMount (or NSAFE\_componentWillMount)
* componentWillReceiveProps (or UNSAFE\_componentWillReceiveProps)
* componentWillUpdate (or UNSAFE\_componentWillUpdate)
* getDerivedStateFromProps
* shouldComponentUpdate
* render
* setState ์๋ฐ์ดํธ ํจ์ (์ฒซ ๋ฒ์งธ ์ธ์)

์์ ๋ฉ์๋๋ค์ ์ฌ๋ฌ ๋ฒ ํธ์ถ๋  ์ ์๊ธฐ ๋๋ฌธ์, ๋ถ์์ฉ์ ํฌํจํ์ง ์๋ ๊ฒ์ด ์ค์ํฉ๋๋ค. ์ด ๊ท์น์ ๋ฌด์ํ  ๊ฒฝ์ฐ, ๋ฉ๋ชจ๋ฆฌ ๋์ ํน์ ์๋ชป๋ ์ ํ๋ฆฌ์ผ์ด์ ์ํ ๋ฑ ๋ค์ํ ๋ฌธ์ ๋ฅผ ์ผ์ผํฌ ๊ฐ๋ฅ์ฑ์ด ์์ต๋๋ค. ๋ถํํ๋, ๋ณดํต ์ด๋ฌํ ๋ฌธ์ ๋ค์ ์์ธกํ ๋๋ก ๋์ํ์ง ์๊ธฐ ๋๋ฌธ์ ๋ฐ๊ฒฌํ๋ ๊ฒ์ด ์ด๋ ค์ธ ์ ์์ต๋๋ค.

Strict ๋ชจ๋๊ฐ ์๋์ผ๋ก ๋ถ์์ฉ์ ์ฐพ์์ฃผ๋ ๊ฒ์ ๋ถ๊ฐ๋ฅํฉ๋๋ค. ํ์ง๋ง, ์กฐ๊ธ ๋ ์์ธกํ  ์ ์๊ฒ๋ ๋ง๋ค์ด์ ๋ฌธ์ ๊ฐ ๋๋ ๋ถ๋ถ์ ๋ฐ๊ฒฌํ  ์ ์๊ฒ ๋์์ค๋๋ค. ์ด๋ ์๋์ ํจ์๋ฅผ ์๋์ ์ผ๋ก ์ด์ค์ผ๋ก ํธ์ถํ์ฌ ์ฐพ์ ์ ์์ต๋๋ค.

ํด๋์ค ์ปดํฌ๋ํธ์ constructor, render ๊ทธ๋ฆฌ๊ณ  shouldComponentUpdate ๋ฉ์๋ ํด๋์ค ์ปดํฌ๋ํธ์ getDerivedStateFromProps static ๋ฉ์๋ ํจ์ ์ปดํฌ๋ํธ ๋ฐ๋ State updater ํจ์ (setState์ ์ฒซ ๋ฒ์งธ ์ธ์) useState, useMemo ๊ทธ๋ฆฌ๊ณ  useReducer์ ์ ๋ฌ๋๋ ํจ์ ์ฃผ์

๊ฐ๋ฐ ๋ชจ๋์์๋ง ์ ์ฉ๋ฉ๋๋ค. ์๋ช์ฃผ๊ธฐ ๋ฉ์๋๋ค์ ํ๋ก๋์ ๋ชจ๋์์ ์ด์ค์ผ๋ก ํธ์ถ๋์ง ์์ต๋๋ค.

์๋ฅผ ๋ค์ด, ์๋์ ์ฝ๋๋ฅผ ์๊ฐํด๋ด์๋ค.

```jsx
class TopLevelRoute extends React.Component {
  constructor(props) {
    super(props);

    SharedApplicationState.recordEvent('ExampleComponent');
  }
}
```

์ผํ ๋ณด๋ฉด ์ด ์ฝ๋์๋ ๋ฌธ์ ๊ฐ ์์ด ๋ณด์๋๋ค. ํ์ง๋ง, SharedApplicationState.recordEvent์ ์ฐ์ฐ ๊ฒฐ๊ณผ๊ฐ ๊ณ์ ๋ฌ๋ผ์ง๋ค๋ฉด, ์ด ์ปดํฌ๋ํธ๋ฅผ ์ฌ๋ฌ ๋ฒ ์ธ์คํด์ค ํํ์ ๋ ์ ํ๋ฆฌ์ผ์ด์์ ์ํ๋ฅผ ์๋ชป๋ ๋ฐฉํฅ์ผ๋ก ์ด๋ ์ ์์ต๋๋ค. ์ด์ ๊ฐ์ ์ดํดํ๊ธฐ ์ด๋ ค์ด ๋ฒ๊ทธ๋ค์ ๊ฐ๋ฐ ์ค์ ๋ํ๋์ง ์์ ์๋ ์๊ณ , ์ผ๊ด์ฑ์ด ์์ด ๋ฐ๊ฒฌํ์ง ๋ชปํ  ์๋ ์์ต๋๋ค.

์ปดํฌ๋ํธ์ constructor์ ๊ฐ์ ๋ฉ์๋๋ฅผ ์๋์ ์ผ๋ก ๋ ๋ฒ ํธ์ถํ๋ฉด strict mode๊ฐ ์ด์ ๊ฐ์ ํจํด์ ์ฝ๊ฒ ์ฐพ์ ์ ์๋๋ก ํฉ๋๋ค.

```plain-text
์ฃผ์

In React 17, React automatically modifies the console methods like console.log() to silence the logs in the second call to lifecycle functions. However, it may cause undesired behavior in certain cases where a workaround can be used.

Starting from React 18, React does not suppress any logs. However, if you have React DevTools installed, the logs from the second call will appear slightly dimmed. React DevTools also offers a setting (off by default) to suppress them completely.
```

## ๋ ๊ฑฐ์ context API ๊ฒ์ฌ

๋ ๊ฑฐ์ context API๋ ์ค๋ฅ๊ฐ ๋ฐ์ํ๊ธฐ ์ฌ์ ์ดํ ๋ฆด๋ฆฌ์ฆ์์ ์ญ์ ๋  ์์ ์๋๋ค. ๋ชจ๋  16.x ๋ฒ์ ์์ ์ฌ์ ํ ๋์๊ฐ์ง๋ง, Strict ๋ชจ๋์์๋ ์๋์ ๊ฐ์ ๊ฒฝ๊ณ  ๋ฉ์์ง๋ฅผ ๋ธ์ถํฉ๋๋ค.

![img](https://ko.reactjs.org/static/fca5c5e1fb2ef2e2d59afb100b432c12/1e088/warn-legacy-context-in-strict-mode.png)

warn legacy context in strict mode ์๋ก์ด context API ๋ฌธ์๋ฅผ ์ฐธ์กฐํ์ฌ ์๋ก์ด ๋ฒ์ ์ผ๋ก ๋ง์ด๊ทธ๋ ์ด์ํ์๊ธธ ๋ฐ๋๋๋ค.

## Ensuring reusable state

In the future, weโd like to add a feature that allows React to add and remove sections of the UI while preserving state. For example, when a user tabs away from a screen and back, React should be able to immediately show the previous screen. To do this, React support remounting trees using the same component state used before unmounting.

This feature will give React better performance out-of-the-box, but requires components to be resilient to effects being mounted and destroyed multiple times. Most effects will work without any changes, but some effects do not properly clean up subscriptions in the destroy callback, or implicitly assume they are only mounted or destroyed once.

To help surface these issues, React 18 introduces a new development-only check to Strict Mode. This new check will automatically unmount and remount every component, whenever a component mounts for the first time, restoring the previous state on the second mount.

To demonstrate the development behavior youโll see in Strict Mode with this feature, consider what happens when React mounts a new component. Without this change, when a component mounts, React creates the effects:

```plain-text
* React mounts the component.
  * Layout effects are created.
  * Effects are created.
```

With Strict Mode starting in React 18, whenever a component mounts in development, React will simulate immediately unmounting and remounting the component:

```plain-text
* React mounts the component.
    * Layout effects are created.
    * Effect effects are created.
* React simulates effects being destroyed on a mounted component.
    * Layout effects are destroyed.
    * Effects are destroyed.
* React simulates effects being re-created on a mounted component.
    * Layout effects are created
    * Effect setup code runs
```

On the second mount, React will restore the state from the first mount. This feature simulates user behavior such as a user tabbing away from a screen and back, ensuring that code will properly handle state restoration.

When the component unmounts, effects are destroyed as normal:

```plain-text
* React unmounts the component.
  * Layout effects are destroyed.
  * Effect effects are destroyed.
```

Unmounting and remounting includes:

* componentDidMount
* componentWillUnmount
* useEffect
* useLayoutEffect
* useInsertionEffect

```plain-text
Note:
This only applies to development mode, production behavior is unchanged.
```
