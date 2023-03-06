# 🍆 usehooks-ts

usehooks-ts는 타입스크립트로 작성된 재사용 가능한 React 훅의 모음입니다. 이러한 후크는 React 애플리케이션의 일반적인 사용 사례를 단순화하도록 설계되었으며 다른 React 라이브러리 및 프레임워크와 함께 사용할 수 있습니다.

사용훅에 포함된 일부 훅은 다음과 같습니다:

`useDebounce`: 지정된 시간 동안 값이나 함수를 디바운스하는 훅입니다.

`useLocalStorage`: 로컬 스토리지에서 데이터를 저장하고 검색할 수 있는 훅입니다.

`useOnClickOutside`: 특정 요소 외부의 클릭을 감지하는 훅입니다.

`useScrollDirection`: 스크롤 방향을 감지하는 훅입니다.

`useWindowSize`: 창 크기를 감지하는 훅입니다.

사용훅의 모든 후크는 사용하기 쉽고 특정 요구에 맞게 사용자 정의할 수 있도록 설계되었습니다. 또한 잘 문서화되어 있고 테스트를 거쳤기 때문에 예상대로 작동할 것이라는 확신을 가질 수 있습니다.

프로젝트에서 사용훅을 사용하려면 NPM 또는 Yarn을 통해 설치하고 사용하려는 훅을 임포트한 다음 컴포넌트에서 사용을 시작하면 됩니다. 예를 들어, 사용 디바운스 후크를 사용하는 방법은 다음과 같습니다:

```javascript
import { useState, useEffect } from 'react';
import { useDebounce } from 'usehooks-ts';

function MyComponent() {
  const [searchTerm, setSearchTerm] = useState('');
  const debouncedSearchTerm = useDebounce(searchTerm, 500);

  useEffect(() => {
    // Make API call with debounced search term
  }, [debouncedSearchTerm]);

  return (
    <input
      type="text"
      value={searchTerm}
      onChange={(e) => setSearchTerm(e.target.value)}
    />
  );
}
```

이 예제에서는 API 호출을 하기 전에 useDebounce 훅을 사용하여 searchTerm 상태 변수를 디바운스하고 있습니다. 이렇게 하면 API 호출이 너무 자주 이루어지지 않아 성능이 향상되고 불필요한 네트워크 요청을 줄일 수 있습니다.
