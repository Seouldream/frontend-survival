# 🌶 ReadableStream

ReadableStream은 소스에서 읽을 수 있는 데이터 스트림을 나타내는 JavaScript 인터페이스입니다. 이 인터페이스는 자바스크립트에서 스트리밍 데이터로 작업하기 위한 인터페이스 및 클래스 집합인 Streams API의 일부입니다.

ReadableStream은 네트워크 소켓, 파일 및 기타 스트림을 포함한 다양한 소스에서 데이터를 읽는 데 사용할 수 있습니다. 청크 단위로 데이터를 읽을 수 있는 간단하고 유연한 인터페이스를 제공하여 대용량 파일이나 실시간 데이터를 처리하는 데 유용할 수 있습니다.

다음은 ReadableStream을 사용하여 네트워크 요청에서 데이터를 읽는 방법의 예시입니다:

```javascript
const response = await fetch('https://example.com/data.json');
const stream = response.body;

const reader = stream.getReader();

while (true) {
  const { done, value } = await reader.read();
  if (done) {
    break;
  }
  console.log(value);
}
```

이 코드는 네트워크 요청의 응답 본문에서 ReadableStream을 생성한 다음 스트림에서 데이터를 읽을 리더를 생성합니다. `read()` 메서드는 리더에서 루프로 호출되어 스트림의 데이터를 청크 단위로 읽습니다. 스트림의 끝에 도달하면 결과 객체의 done 속성이 true가 되고 루프가 종료됩니다.

ReadableStream 인터페이스는 스트림을 취소하는 `cancel()`, 데이터를 다른 스트림으로 전달하는 `pipeTo()`, 스트림을 두 개의 분기로 분할하는 `tee()` 등 스트리밍 데이터 작업을 위한 몇 가지 다른 메서드와 프로퍼티를 제공합니다.

전반적으로 ReadableStream은 자바스크립트에서 스트리밍 데이터로 작업하기 위한 강력하고 유연한 도구입니다. 간단하고 일관된 인터페이스를 통해 다양한 소스의 대용량 파일과 실시간 데이터를 쉽게 처리할 수 있습니다.
