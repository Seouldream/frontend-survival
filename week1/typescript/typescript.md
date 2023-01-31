# 🐣 2. **TypeScript**

## TypeScript: 정적 타입 검사자 (TypeScript: A Static Type Checker)

JavaScript가 가진 단점을 극복하기 위해 나타난 언어.

프로그램을 실행시키지 않으면서 코드의 오류를 검출하는 것을 정적 검사라고 하는데 타입스크립트는 어떤 것이 오류인지와 어떤 것이 연산 되는 값에 기인하지 않음을 정하는 것이 정적 타입 검사를 기반으로 오류를 찾아준다.

ex) 자바 스크립트는 동일 연산자는 (==) 인수를 강제로 변환하여(coerces), 예기치 않은 동작을 유발하거나 존재하지 않는 프로퍼티의 접근을 허용한다.


## 1. 타입 지정
```tsx
let name: string;
let age: number;

name = '홍길동';
age = 13;

name = 13;
age = '홍길동';

let human: {
  name: string;
  age: number;
};

human = { name: '홍길동', age: 13 };
```

## 2. 타입과 인터페이스의 차이점

타입과 인터페이스는 매우 유사하며, 대부분의 경우 둘 중 하나를 자유롭게 선택하여 사용할 수 있다. interface가 가지는 대부분의 기능은 type에서도 동일하게 사용 가능하다. 

> 이 둘의 가장 핵심적인 차이는, 타입은 새 프로퍼티를 추가하도록 개방될 수 없는 반면, 인터페이스의 경우 항상 확장될 수 있다는 점이다.

### 인터페이스

인터페이스 확장하기
```tsx 
interface Animal {
  name: string
}

interface Bear extends Animal {
  honey: boolean
}

const bear = getBear()
bear.name
bear.honey
```

기존의 인터페이스에 새 필드를 추가하기

```tsx 
interface Window {
  title: string
}

interface Window {
  ts: TypeScriptAPI
}

const src = 'const a = "Hello World"';
window.ts.transpileModule(src, {});
```

### 타입

교집합을 통하여 타입 확장하기

```tsx 
type Animal = {
  name: string
}

type Bear = Animal & {
  honey: Boolean
}

const bear = getBear();
bear.name;
bear.honey;
        
```
```tsx
type Window = {
  title: string
}

type Window = {
  ts: TypeScriptAPI
}

 // Error: Duplicate identifier
```
