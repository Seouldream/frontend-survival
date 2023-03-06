# 🫑 Hooks

### useState

useState는 함수형 컴포넌트에 state를 추가할 수 있는 내장된 React Hook입니다. 상태는 입력 필드의 값, 모달의 가시성 또는 API에서 가져온 데이터와 같이 시간이 지남에 따라 변경되는 데이터입니다.

useState를 사용하려면 먼저 'react' 라이브러리에서 가져와야 합니다:



```javascript
import React, { useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

이 예제에서는 useState를 사용해 컴포넌트에 카운트 상태 변수를 추가합니다. 0을 초기 상태 값으로 useState에 전달하여 카운트를 0에서 시작합니다.

useState 함수는 현재 상태 값과 상태 값을 업데이트하는 함수의 두 가지 값을 가진 배열을 반환합니다. 배열 해체를 사용하여 이 값을 각각 count와 setCount 변수에 할당합니다.

그런 다음 컴포넌트에서 이 변수를 사용하여 현재 카운트 값을 표시하고 버튼이 클릭될 때 업데이트합니다. 버튼이 클릭되면 새로운 카운트 값(이 경우 카운트 + 1)으로 setCount 함수를 호출하고, React는 새로운 카운트 값으로 컴포넌트를 다시 렌더링합니다.

전반적으로, useState는 React 함수형 컴포넌트에서 상태를 관리하는 간단하고 강력한 방법입니다. 클래스 컴포넌트로 변환하거나 상위 컴포넌트를 사용할 필요 없이 컴포넌트에 상태를 추가할 수 있습니다.



### useEffect

는 함수형 컴포넌트에서 사이드 이펙트를 수행할 수 있도록 해주는 내장된 React Hook입니다. 사이드 이펙트란 API에서 데이터를 불러오거나 DOM을 업데이트하거나 이벤트 리스너를 설정하는 등 컴포넌트 외부에 영향을 미치는 모든 액션을 말합니다.

useEffect를 사용하려면 먼저 'react' 라이브러리에서 가져와야 합니다:

```javascript
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

```

이 예제에서는 count 상태 변수가 변경될 때마다 문서 제목을 업데이트하기 위해 useEffect를 사용하고 있습니다. 사용 효과 함수 내에서 document.title = You clicked ${count} times\`\`를 호출하여 이를 수행합니다.

사용 효과 함수에는 부수 효과를 수행하는 함수와 선택적 종속성 배열이라는 두 가지 인수가 있습니다. 부수 효과 함수는 컴포넌트가 처음 렌더링된 후 실행되고, 종속성 중 하나가 변경될 때마다 다시 실행됩니다. 이 예제에서는 종속성을 전달하지 않았으므로 모든 렌더링에서 부작용 함수가 실행됩니다.

전반적으로, useEffect는 React 함수형 컴포넌트에서 사이드 이펙트를 수행하는 강력한 방법입니다. 컴포넌트 내부에 부수효과 로직을 캡슐화할 수 있으므로 추론하고 테스트하기가 더 쉬워집니다. 하지만 잘못 사용하면 성능 문제가 발생할 수 있으므로 사용 방법에 주의를 기울여야 합니다.



### useContext

useContext는 함수형 컴포넌트에서 컨텍스트를 사용할 수 있게 해주는 내장된 React Hook입니다. 컨텍스트는 모든 레벨에서 수동으로 소품을 전달할 필요 없이 컴포넌트 트리를 통해 데이터를 전달할 수 있는 방법을 제공합니다.

useContext를 사용하려면 먼저 createContext 함수를 사용해 컨텍스트를 생성해야 합니다:

```javascript
const MyContext = React.createContext(defaultValue);
```

defaultValue 인수는 선택 사항이며 컴포넌트 트리에서 공급자를 찾을 수 없는 경우 컨텍스트의 기본값을 지정합니다.

그런 다음 MyContext.Provider 컴포넌트를 사용하여 컴포넌트의 하위 트리에 컨텍스트 값을 제공할 수 있습니다:

```javascript
<MyContext.Provider value={/* context value */}>
  {/* components that consume the context */}
</MyContext.Provider>
```

마지막으로, useContext 함수를 사용하여 함수형 컴포넌트에서 컨텍스트 값을 사용할 수 있습니다:

```javascript
function MyComponent() {
  const contextValue = useContext(MyContext);
  // ...
}
```

이 예시에서는 useContext를 사용하여 MyComponent 함수형 컴포넌트에서 MyContext 컨텍스트의 값을 사용합니다. contextValue 변수에는 컴포넌트 트리에서 가장 가까운 MyContext.Provider 컴포넌트가 제공하는 컨텍스트 값이 포함됩니다.

컨텍스트와 useContext를 사용하면 React 컴포넌트 트리에서 데이터와 기능을 공유할 수 있는 강력한 방법이 될 수 있습니다. 하지만 컴포넌트 간에 불필요한 결합을 피하기 위해 신중하게 사용하고 남용을 피하는 것이 중요합니다.



### useRef

useRef는 컴포넌트 렌더링 전반에 걸쳐 지속되는 값에 대한 변경 가능한 참조를 생성할 수 있는 내장된 React Hook입니다. state와 달리, useRef 값의 변경은 컴포넌트의 재렌더링을 트리거하지 않습니다.

useRef를 사용하려면 먼저 'react' 라이브러리에서 가져와야 합니다:

<pre class="language-javascript"><code class="lang-javascript"><strong>import React, { useRef } from 'react';
</strong><strong>
</strong><strong>function Example() {
</strong>  const inputRef = useRef(null);

  function handleClick() {
    inputRef.current.focus();
  }

  return (
    &#x3C;div>
      &#x3C;input ref={inputRef} type="text" />
      &#x3C;button onClick={handleClick}>
        Focus Input
      &#x3C;/button>
    &#x3C;/div>
  );
}
</code></pre>

이 예제에서는 useRef를 사용하여 입력 요소에 대한 참조를 생성합니다. 이 참조를 입력 요소의 ref 속성으로 전달한 다음 inputRef 객체의 현재 속성을 사용하여 handleClick 함수에서 입력 요소에 액세스합니다.

useRef는 종종 DOM 요소를 참조하는 데 사용되지만 컴포넌트 렌더링에서 유지되어야 하는 변경 가능한 값을 저장하는 데에도 사용할 수 있습니다. 예를 들어, state 변수의 이전 값을 저장하거나 클래스 컴포넌트의 인스턴스를 저장하는 데 useRef를 사용할 수 있습니다.

전반적으로, useRef는 React 함수형 컴포넌트에서 변경 가능한 값으로 작업하는 데 유용한 도구입니다. 하지만 잘못 사용하면 혼란스럽고 디버깅하기 어려운 코드를 만들 수 있으므로 신중하게 사용하고 남용하지 않는 것이 중요합니다.

### useLayoutEffect

useLayoutEffect는 useEffect 훅과 유사하지만 브라우저에서 모든 DOM 변경이 적용된 후에 동기적으로 실행되는 내장된 React 훅입니다. 따라서 브라우저가 화면을 그리기 전에 동기적으로 적용해야 하는 DOM 측정 및 업데이트를 수행하는 데 유용합니다.

useLayoutEffect의 구문은 useEffect와 유사하지만 효과의 타이밍이 다릅니다:

```javascript
import React, { useLayoutEffect } from 'react';

function Example() {
  useLayoutEffect(() => {
    // effect code here
  });

  return <div>...</div>;
}
```

이 예제에서는 브라우저가 보류 중인 모든 DOM 변형을 적용한 후 화면을 페인팅하기 전에 useLayoutEffect 함수가 실행됩니다. 이 함수는 모든 변경이 적용될 때까지 값이 정확하지 않을 수 있으므로 DOM 요소의 크기나 위치에 따라 달라지는 측정이나 계산을 수행하는 데 유용할 수 있습니다.

한 가지 주의할 점은 useLayoutEffect는 효과가 완료될 때까지 브라우저의 페인팅 프로세스를 차단하기 때문에 사용효과보다 비용이 더 많이 들 수 있다는 점입니다. 대부분의 사용 사례에서는 useEffect로 충분하지만, 컴포넌트 상태 변경에 반응하여 동기식 DOM 업데이트를 수행해야 하는 경우에는 useLayoutEffect가 유용한 도구가 될 수 있습니다.

전반적으로, useLayoutEffect는 React에서 브라우저의 레이아웃과 페인팅 프로세스를 다루는 데 강력한 도구이지만 애플리케이션의 렌더링 성능을 저하시키지 않도록 신중하게 사용해야 합니다.
