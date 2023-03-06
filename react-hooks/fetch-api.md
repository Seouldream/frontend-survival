# 🥒 Fetch API

Fetch API는 HTTP 프로토콜을 사용하여 서버에 네트워크 요청을 하기 위한 최신 JavaScript 인터페이스입니다. 이 인터페이스는 수년 동안 웹 브라우저에서 비동기 네트워크 요청을 하는 표준 방법으로 사용되어 온 구형 XMLHttpRequest(XHR) API를 대체할 수 있는 더 간단하고 유연한 대안을 제공합니다.

Fetch API는 자바스크립트 프로미스를 사용하여 요청을 하고 응답을 처리하기 위한 간단한 구문을 제공합니다. 이를 통해 개발자는 텍스트, JSON, HTML, 이미지 및 기타 바이너리 데이터를 포함한 다양한 리소스에 대한 요청을 할 수 있습니다. Fetch API는 스트리밍 응답도 지원하므로 대용량 파일이나 실시간 데이터를 처리하는 데 유용할 수 있습니다.

다음은 Fetch API를 사용하여 GET 요청을 하는 방법의 예입니다:

```javascript
fetch('https://example.com/data.json')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));

```

Fetch API는 POST 요청, 요청 헤더 설정, 오류 및 시간 초과 처리도 지원합니다. 서버 및 API와 상호 작용해야 하는 최신 웹 애플리케이션을 구축하기 위한 강력한 도구입니다.

전반적으로 Fetch API는 JavaScript를 사용하여 웹 브라우저에서 네트워크 요청을 할 수 있는 강력하고 유연한 도구입니다. 더 간단한 구문과 프로미스 지원으로 최신 웹 개발에 널리 사용됩니다.
