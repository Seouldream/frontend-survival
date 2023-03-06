# 🌶 Promise

자바스크립트에서 프로미스는 비동기 연산의 최종 완료(또는 실패)와 그 결과 값을 나타내는 객체입니다. 프로미스는 최신 자바스크립트의 핵심 기능으로, 특히 네트워크 요청과 비동기 데이터 처리를 위해 웹 개발에서 널리 사용됩니다.

프로미스에는 세 가지 가능한 상태가 있습니다:

Pending : 프로미스가 생성되어 비동기 작업이 완료되기를 기다리는 초기 상태입니다.

Fulfilled: 비동기 작업이 성공적으로 완료되고 프로미스에 결과 값이 있는 상태입니다.

Rejected: 비동기 작업이 실패한 상태이며, 프로미스에 실패 이유가 있는 상태입니다.&#x20;

프라미스는 비동기 연산을 정의하는 단일 함수 인수를 받는 프라미스 생성자를 사용하여 생성됩니다. 이 함수는 연산이 성공하면 resolve() 함수를 호출하고, 실패하면 reject() 함수를 호출해야 합니다. 그때() 메서드는 프로미스에서 호출하여 성공적인 완료를 처리하고, 캐치() 메서드는 호출하여 실패를 처리할 수 있습니다.

다음은 자바스크립트에서 프로미스를 생성하고 사용하는 방법에 대한 예시입니다:

```javascript
const myPromise = new Promise((resolve, reject) => {
  // Perform some asynchronous operation
  // If successful, call resolve() with the result
  // If failed, call reject() with an error message
});

myPromise.then(result => {
  // Handle the successful completion
}).catch(error => {
  // Handle the failure
});
```

이 코드는 비동기 작업을 나타내는 새 Promise 객체를 생성합니다. 그때() 메서드는 성공적인 완료를 처리하기 위해 프로미스에서 호출되고, 실패를 처리하기 위해 catch() 메서드가 호출됩니다.

프로미스는 성공과 실패를 처리하는 간단하고 일관된 방법을 제공하고 중첩된 콜백 함수로 인해 발생할 수 있는 "콜백 지옥"을 피할 수 있기 때문에 JavaScript에서 비동기 연산을 처리하는 데 중요한 도구입니다.
