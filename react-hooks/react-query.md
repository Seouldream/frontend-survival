# 🍳 React Query

React Query는 React 애플리케이션에서 원격 데이터를 관리하기 위한 라이브러리입니다. API 및 기타 원격 데이터 소스에서 데이터를 가져오고, 캐싱하고, 업데이트하기 위한 일련의 후크와 유틸리티를 제공합니다.

React Query의 주요 기능은 다음과 같습니다:

자동 캐시 관리: React Query는 자동으로 데이터를 캐시하고 새 데이터를 가져올 때 캐시를 업데이트합니다. 또한 캐시를 수동으로 관리할 수 있는 유틸리티도 제공합니다.

실시간 업데이트: React Query는 API를 자동으로 폴링하고 필요에 따라 캐시를 업데이트하여 실시간 업데이트를 지원합니다.

쿼리 무효화: React Query는 쿼리 무효화 및 데이터 리페칭을 위한 유틸리티를 제공합니다.

서스펜스 모드 지원: React Query는 데이터를 불러오는 동안 로딩 상태를 표시하여 사용자 경험을 개선할 수 있는 React의 Suspense 모드를 지원합니다.

페이지 매김 지원: React Query는 페이지 매김을 기본적으로 지원하므로 페이지가 매겨진 데이터를 쉽게 가져오고 표시할 수 있습니다.

다음은 React Query를 사용해 데이터를 불러오고 표시하는 방법의 예시입니다:

```javascript
import { useQuery } from 'react-query';

function MyComponent() {
  const { data, isLoading, isError } = useQuery('todos', async () => {
    const response = await fetch('/api/todos');
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  });

  if (isLoading) {
    return <div>Loading data...</div>;
  }

  if (isError) {
    return <div>Error loading data</div>;
  }

  return (
    <div>
      {data.map(item => (
        <div key={item.id}>{item.name}</div>
      ))}
    </div>
  );
}
```

이 예제에서는 사용 쿼리 훅을 사용하여 API 엔드포인트에서 데이터를 가져옵니다. 쿼리에 대한 고유 키와 데이터를 가져오는 비동기 함수를 전달하고 있습니다. 그러면 후크가 데이터를 가져와서 데이터, isLoading 및 isError 프로퍼티가 포함된 객체를 반환합니다. 그런 다음 isLoading 및 isError 프로퍼티의 상태에 따라 데이터 또는 오류 메시지를 렌더링합니다.

React Query는 React 애플리케이션에서 원격 데이터를 관리하기 위한 강력한 도구입니다. 캐싱과 실시간 업데이트 기능을 통해 원격 데이터로 쉽게 작업하면서도 뛰어난 사용자 경험을 제공할 수 있습니다.
