# 🥕 React.StrictMode

React.StrictMode는 애플리케이션 코드의 잠재적인 문제를 런타임에 추가로 검사하는 데 사용할 수 있는 React에 내장된 컴포넌트입니다. 컴포넌트를 React.StrictMode로 감싸면 React는 안전하지 않은 수명 주기 메서드, 레거시 문자열 참조 사용 등과 같은 코드의 잠재적 문제를 강조하기 위해 다양한 검사를 수행합니다.

다음은 React.StrictMode를 사용하는 방법의 예시입니다:

```javascript
import React from 'react';

function App() {
  return (
    <React.StrictMode>
      <div>My App</div>
    </React.StrictMode>
  );
}
```

이 예제에서는 전체 App 컴포넌트를 React.StrictMode로 감싸고 있습니다. 이렇게 하면 애플리케이션 코드에서 잠재적인 문제를 포착하는 데 도움이 되는 추가 런타임 검사를 활성화할 수 있습니다.
