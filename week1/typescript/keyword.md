# REPL
    REPL은 Read-Eval-Print-Loop의 약자로 애플리케이션 실행 상태에서 사용자가 입력한 명령어(소스코드)를 읽고(Read) 명령어를 평가(Eval)하고 결과를 출력(Print)한 다음 다시 입력을 기다리는 상태로 돌아가는 과정을 반복(Loop)한다.
    즉 입력 후 즉각적으로 결과를 볼 수 있는 방식

    ex) 터미널에서 Node라고 치면 즉각적으로 자바스크립트를 사용할 수 있음

# TypeScript
    타입스크립트(TypeScript)는 자바스크립트의 슈퍼셋인 오픈소스 프로그래밍 언어이다. 마이크로소프트에서 개발, 유지하고 있으며 엄격한 문법을 지원한다. C#의 리드 아키텍트이자 델파이, 터보 파스칼의 창시자인 Anders Hejlsberg가 개발에 참여한다. 클라이언트 사이드와 서버 사이드를 위한 개발에 사용할 수 있다.

타입스크립트는 자바스크립트 엔진을 사용하면서 커다란 애플리케이션을 개발할 수 있게 설계된 언어이다. 자바스크립트의 슈퍼셋이기 때문에 자바스크립트로 작성된 프로그램이 타입스크립트 프로그램으로도 동작한다.
타입스크립트에서 자신이 원하는 타입을 정의하고 프로그래밍을 하면 자바스크립트로 컴파일되어 실행할 수 있다.
타입스크립트는 모든 운영 체제, 모든 브라우저, 모든 호스트에서 사용 가능한 오픈 소스이다.

## 인터페이스와 타입의 차이
### 선언적 확장
interface에서 할 수 있는 대부분의 기능들은 type에서 가능하지만, 한 가지 중요한 차이점은 type은 새로운 속성을 추가하기 위해서 다시 같은 이름으로 선언할 수 없지만, interface는 항상 선언적 확장이 가능하다는 것이다.
### 타입 추론
    타입 추론이란 TypeScript에서 명시적인 타입 표기가 없을 때 타입 정보를 제공하기 위해 사용되는 것이다.

쉽게 말하면 자동으로 타입을 결정해주는 것이라고 보면 된다.
```tsx
let x = 3; // let x: number
let y = "4"; // let y: string
```
이런 식으로 javascript처럼 사용하면 typescript는 자동적으로 타입을 추론하여 알맞은 타입을 결정한다.

그리고 여러 타입을 동시에 사용할 경우 최적 공통 타입을 알아서 계산해준다.

```tsx
let x = [0, 1, null]; // let x: (number | null)[]
```
또한 문맥을 체크하여 타입을 결정짓기도 한다.

# Union Type vs Intersection Type

### 🏷 요약
Intersection → And : A & B : A타입이면서 B타입, 즉 두 특성 모두를 지닌 타입

Union → Or : A | B : A타입, B 타입 둘 중 하나, 즉 둘 중 어느 하나만이 올 수 있는 타입

## 📝 Union Type
```tsx
let one: string | number | boolean;
 
one = 1;
one = '1';
one = true;
```
- | 를 사용
- Type A, Type B가 있을 때 A와 B를 유니온 하면 A타입 또는 B 타입 둘 중 하나
one: string이거나 number 둘 중 하나

## 📕 Union Type 언제 사용할까?
```tsx
type A = string | number;
 
// An interface can only extend an object type or intersection of object types with statically known members.
interface StrOrNum extends A {
    a: string;
}
 
// Ok
type StrOrNum = {
    a: string;
} & (string | number);
interface Animal {
  eat: () => void;
  sleep: () => void;
}
 
interface Human {
  think: () => void;
}
 
type Developer = (Animal | Human) & {
  work: () => void;
};
```
여러 타입 중 하나가 올 것이라고 가정할 때 사용
단, 인터페이스에 유니온 타입을 사용하는 경우 인터페이스 유니온 타입을 확장하지 못함
이럴 때는 type alias와 &를 사용해야 함
 

## 📕 Union Type는 동시에 여러 타입이 될 수 없다.
```tsx
type Human = {
    think: () => void;
};
 
type Dog = {
    bark: () => void;
}
declare function getEliceType(): Human | Dog; // 반환 타입이 Human or Dog인 getEliceType 함수
 
const elice = getEliceType(); // getEliceType 함수를 호출한 결과를 elice 라는 변수에 할당
 
// Property 'think' does not exist on type 'Human | Dog'.
elice.think();
 
// Property 'bark' does not exist on type 'Human | Dog'.
elice.bark();
```
elice를 Human or Dog라는 유니온 타입으로 만들어 주어도 think, bark 둘 중 어느 것도 사용하지 못함
why? → elice가 런타임에서 Human인지 Dog인지 확신할 수 없기 때문에
elice.think() 함수를 호출할 때 elice가 Human이라면 괜찮지만 Dog라면 think를 호출할 수 없기 때문에 컴파일 단계에서 에러
해결 방법 : 타입 가드 ⇒ elice가 Human 일 때 think함수를, Dog 일 때 bark함수를
 

## 📝 Intersection Type
```tsx
type Human = {
    think: () => void;
};
 
type Developer = {
    word: () => void;
}
 
const elice: Human & Developer = {
    think() {
        console.log("생각 중");
    } ,
    word() {
        console.log("업무 중");
    } 
}
```
기존 타입을 대체하지 않으면서 기존 타입에 새로운 필드를 추가하고 싶을 때 사용
교차 타입(Intersection Type)은 &(앰퍼샌드)를 사용한다.
Type A, Type B가 있을 때 A와 B를 인터섹션 하면 A타입이면서 B타입이라는 의미
즉, Elice는 Human이면서 Developer라서 두 개의 속성을 동시에 가질 수 있다.
 

## 📕 Intersection Type는 언제 사용할까?
```tsx
type Human = {
    think: () => void;
};
 
type Developer = {
    word: () => void;
}
 
type Student = {
    study: () => void;
}
 
const elice: Human & Developer & Student = {
    think() {
        console.log("생각 중");
    } ,
    word() {
        console.log("업무 중"); 
    } ,
    study() {
        console.log("공부 중");
    } 
}
```
Intersection Type은 기존 타입을 대체하지 않으면서 기존 타입에 새로운 필드를 추가하고 싶을 때 사용 ⇒ 확장하고 싶을 때 사용
기존의 Human & Developer 타입의 elice에 student 타입을 추가해 기존 타입은 변경하지 않고 확장 가능
 

## 📕 Intersection Type 주의할 점 : 각 타입에 겹치는 필드가 있다면 어떻게 될까?
🛠 타입이 같을 때 : Ok

```tsx
type Developer = {
    output: string;
    developer: () => void;
}
 
type Designer = {
    output: string;
    design: () => void;
}
 
const 개자이너: Developer & Designer = {
    output: 'sth cool', // ok
    developer() {
        console.log("업무 중");
    },
    design() {
        console.log("업무 중");
    }
}
```
가능
 

### 🛠 타입이 다를 때 : Error
```tsx
type Developer = {
    output: number; // ** 
    developer: () => void;
}
 
type Designer = {
    output: string;
    design: () => void;
}
 
const 개자이너: Developer & Designer = {
    output: 'sth cool', // error
    developer() {
        console.log("업무 중");
    },
    design() {
        console.log("업무 중");
    }
}
```
에러
 

### 🛠 타입이 포함관계일 때 : Ok or Error
```tsx
type Developer = {
    output: number; // ** 
    developer: () => void;
}
 
type Designer = {
    output: string | number; // ** 
    design: () => void;
}
 
const 개자이너: Developer & Designer = {
    // output: 'sth cool', // error
    output: 1, // ok (string | number) & number 이라서 number type은 ok!
    developer() {
        console.log("업무 중");
    },
    design() {
        console.log("업무 중");
    }
}
```
(string | number) & number이라서 number type은 ok!
 

