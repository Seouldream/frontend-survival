# ๐ฃ ๊ฐ๋ ์ง๊ณ  ๊ฐ๊ธฐ

## REPL

```
REPL์ Read-Eval-Print-Loop์ ์ฝ์๋ก ์ ํ๋ฆฌ์ผ์ด์ ์คํ ์ํ์์ ์ฌ์ฉ์๊ฐ ์๋ ฅํ ๋ช๋ น์ด(์์ค์ฝ๋)๋ฅผ ์ฝ๊ณ (Read) ๋ช๋ น์ด๋ฅผ ํ๊ฐ(Eval)ํ๊ณ  ๊ฒฐ๊ณผ๋ฅผ ์ถ๋ ฅ(Print)ํ ๋ค์ ๋ค์ ์๋ ฅ์ ๊ธฐ๋ค๋ฆฌ๋ ์ํ๋ก ๋์๊ฐ๋ ๊ณผ์ ์ ๋ฐ๋ณต(Loop)ํ๋ค.
์ฆ ์๋ ฅ ํ ์ฆ๊ฐ์ ์ผ๋ก ๊ฒฐ๊ณผ๋ฅผ ๋ณผ ์ ์๋ ๋ฐฉ์

ex) ํฐ๋ฏธ๋์์ Node๋ผ๊ณ  ์น๋ฉด ์ฆ๊ฐ์ ์ผ๋ก ์๋ฐ์คํฌ๋ฆฝํธ๋ฅผ ์ฌ์ฉํ  ์ ์์
```

## TypeScript

```
ํ์์คํฌ๋ฆฝํธ(TypeScript)๋ ์๋ฐ์คํฌ๋ฆฝํธ์ ์ํผ์์ธ ์คํ์์ค ํ๋ก๊ทธ๋๋ฐ ์ธ์ด์ด๋ค. ๋ง์ดํฌ๋ก์ํํธ์์ ๊ฐ๋ฐ, ์ ์งํ๊ณ  ์์ผ๋ฉฐ ์๊ฒฉํ ๋ฌธ๋ฒ์ ์ง์ํ๋ค. C#์ ๋ฆฌ๋ ์ํคํํธ์ด์ ๋ธํ์ด, ํฐ๋ณด ํ์ค์นผ์ ์ฐฝ์์์ธ Anders Hejlsberg๊ฐ ๊ฐ๋ฐ์ ์ฐธ์ฌํ๋ค. ํด๋ผ์ด์ธํธ ์ฌ์ด๋์ ์๋ฒ ์ฌ์ด๋๋ฅผ ์ํ ๊ฐ๋ฐ์ ์ฌ์ฉํ  ์ ์๋ค.
```

ํ์์คํฌ๋ฆฝํธ๋ ์๋ฐ์คํฌ๋ฆฝํธ ์์ง์ ์ฌ์ฉํ๋ฉด์ ์ปค๋ค๋ ์ ํ๋ฆฌ์ผ์ด์์ ๊ฐ๋ฐํ  ์ ์๊ฒ ์ค๊ณ๋ ์ธ์ด์ด๋ค. ์๋ฐ์คํฌ๋ฆฝํธ์ ์ํผ์์ด๊ธฐ ๋๋ฌธ์ ์๋ฐ์คํฌ๋ฆฝํธ๋ก ์์ฑ๋ ํ๋ก๊ทธ๋จ์ด ํ์์คํฌ๋ฆฝํธ ํ๋ก๊ทธ๋จ์ผ๋ก๋ ๋์ํ๋ค. ํ์์คํฌ๋ฆฝํธ์์ ์์ ์ด ์ํ๋ ํ์์ ์ ์ํ๊ณ  ํ๋ก๊ทธ๋๋ฐ์ ํ๋ฉด ์๋ฐ์คํฌ๋ฆฝํธ๋ก ์ปดํ์ผ๋์ด ์คํํ  ์ ์๋ค. ํ์์คํฌ๋ฆฝํธ๋ ๋ชจ๋  ์ด์ ์ฒด์ , ๋ชจ๋  ๋ธ๋ผ์ฐ์ , ๋ชจ๋  ํธ์คํธ์์ ์ฌ์ฉ ๊ฐ๋ฅํ ์คํ ์์ค์ด๋ค.

### ์ธํฐํ์ด์ค์ ํ์์ ์ฐจ์ด

#### ์ ์ธ์  ํ์ฅ

interface์์ ํ  ์ ์๋ ๋๋ถ๋ถ์ ๊ธฐ๋ฅ๋ค์ type์์ ๊ฐ๋ฅํ์ง๋ง, ํ ๊ฐ์ง ์ค์ํ ์ฐจ์ด์ ์ type์ ์๋ก์ด ์์ฑ์ ์ถ๊ฐํ๊ธฐ ์ํด์ ๋ค์ ๊ฐ์ ์ด๋ฆ์ผ๋ก ์ ์ธํ  ์ ์์ง๋ง, interface๋ ํญ์ ์ ์ธ์  ํ์ฅ์ด ๊ฐ๋ฅํ๋ค๋ ๊ฒ์ด๋ค.

#### ํ์ ์ถ๋ก 

```
ํ์ ์ถ๋ก ์ด๋ TypeScript์์ ๋ช์์ ์ธ ํ์ ํ๊ธฐ๊ฐ ์์ ๋ ํ์ ์ ๋ณด๋ฅผ ์ ๊ณตํ๊ธฐ ์ํด ์ฌ์ฉ๋๋ ๊ฒ์ด๋ค.
```

์ฝ๊ฒ ๋งํ๋ฉด ์๋์ผ๋ก ํ์์ ๊ฒฐ์ ํด์ฃผ๋ ๊ฒ์ด๋ผ๊ณ  ๋ณด๋ฉด ๋๋ค.

```tsx
let x = 3; // let x: number
let y = "4"; // let y: string
```

์ด๋ฐ ์์ผ๋ก javascript์ฒ๋ผ ์ฌ์ฉํ๋ฉด typescript๋ ์๋์ ์ผ๋ก ํ์์ ์ถ๋ก ํ์ฌ ์๋ง์ ํ์์ ๊ฒฐ์ ํ๋ค.

๊ทธ๋ฆฌ๊ณ  ์ฌ๋ฌ ํ์์ ๋์์ ์ฌ์ฉํ  ๊ฒฝ์ฐ ์ต์  ๊ณตํต ํ์์ ์์์ ๊ณ์ฐํด์ค๋ค.

```tsx
let x = [0, 1, null]; // let x: (number | null)[]
```

๋ํ ๋ฌธ๋งฅ์ ์ฒดํฌํ์ฌ ํ์์ ๊ฒฐ์ ์ง๊ธฐ๋ ํ๋ค.

## Union Type vs Intersection Type

#### ๐ท ์์ฝ

Intersection โ And : A & B : Aํ์์ด๋ฉด์ Bํ์, ์ฆ ๋ ํน์ฑ ๋ชจ๋๋ฅผ ์ง๋ ํ์

Union โ Or : A | B : Aํ์, B ํ์ ๋ ์ค ํ๋, ์ฆ ๋ ์ค ์ด๋ ํ๋๋ง์ด ์ฌ ์ ์๋ ํ์

### ๐ Union Type

```tsx
let one: string | number | boolean;
 
one = 1;
one = '1';
one = true;
```

* \| ๋ฅผ ์ฌ์ฉ
* Type A, Type B๊ฐ ์์ ๋ A์ B๋ฅผ ์ ๋์จ ํ๋ฉด Aํ์ ๋๋ B ํ์ ๋ ์ค ํ๋ one: string์ด๊ฑฐ๋ number ๋ ์ค ํ๋

### ๐ Union Type ์ธ์  ์ฌ์ฉํ ๊น?

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

์ฌ๋ฌ ํ์ ์ค ํ๋๊ฐ ์ฌ ๊ฒ์ด๋ผ๊ณ  ๊ฐ์ ํ  ๋ ์ฌ์ฉ ๋จ, ์ธํฐํ์ด์ค์ ์ ๋์จ ํ์์ ์ฌ์ฉํ๋ ๊ฒฝ์ฐ ์ธํฐํ์ด์ค ์ ๋์จ ํ์์ ํ์ฅํ์ง ๋ชปํจ ์ด๋ด ๋๋ type alias์ &๋ฅผ ์ฌ์ฉํด์ผ ํจ

### ๐ Union Type๋ ๋์์ ์ฌ๋ฌ ํ์์ด ๋  ์ ์๋ค.

```tsx
type Human = {
    think: () => void;
};
 
type Dog = {
    bark: () => void;
}
declare function getEliceType(): Human | Dog; // ๋ฐํ ํ์์ด Human or Dog์ธ getEliceType ํจ์
 
const elice = getEliceType(); // getEliceType ํจ์๋ฅผ ํธ์ถํ ๊ฒฐ๊ณผ๋ฅผ elice ๋ผ๋ ๋ณ์์ ํ ๋น
 
// Property 'think' does not exist on type 'Human | Dog'.
elice.think();
 
// Property 'bark' does not exist on type 'Human | Dog'.
elice.bark();
```

elice๋ฅผ Human or Dog๋ผ๋ ์ ๋์จ ํ์์ผ๋ก ๋ง๋ค์ด ์ฃผ์ด๋ think, bark ๋ ์ค ์ด๋ ๊ฒ๋ ์ฌ์ฉํ์ง ๋ชปํจ why? โ elice๊ฐ ๋ฐํ์์์ Human์ธ์ง Dog์ธ์ง ํ์ ํ  ์ ์๊ธฐ ๋๋ฌธ์ elice.think() ํจ์๋ฅผ ํธ์ถํ  ๋ elice๊ฐ Human์ด๋ผ๋ฉด ๊ด์ฐฎ์ง๋ง Dog๋ผ๋ฉด think๋ฅผ ํธ์ถํ  ์ ์๊ธฐ ๋๋ฌธ์ ์ปดํ์ผ ๋จ๊ณ์์ ์๋ฌ ํด๊ฒฐ ๋ฐฉ๋ฒ : ํ์ ๊ฐ๋ โ elice๊ฐ Human ์ผ ๋ thinkํจ์๋ฅผ, Dog ์ผ ๋ barkํจ์๋ฅผ

### ๐ Intersection Type

```tsx
type Human = {
    think: () => void;
};
 
type Developer = {
    word: () => void;
}
 
const elice: Human & Developer = {
    think() {
        console.log("์๊ฐ ์ค");
    } ,
    word() {
        console.log("์๋ฌด ์ค");
    } 
}
```

๊ธฐ์กด ํ์์ ๋์ฒดํ์ง ์์ผ๋ฉด์ ๊ธฐ์กด ํ์์ ์๋ก์ด ํ๋๋ฅผ ์ถ๊ฐํ๊ณ  ์ถ์ ๋ ์ฌ์ฉ ๊ต์ฐจ ํ์(Intersection Type)์ &(์ฐํผ์๋)๋ฅผ ์ฌ์ฉํ๋ค. Type A, Type B๊ฐ ์์ ๋ A์ B๋ฅผ ์ธํฐ์น์ ํ๋ฉด Aํ์์ด๋ฉด์ Bํ์์ด๋ผ๋ ์๋ฏธ ์ฆ, Elice๋ Human์ด๋ฉด์ Developer๋ผ์ ๋ ๊ฐ์ ์์ฑ์ ๋์์ ๊ฐ์ง ์ ์๋ค.

### ๐ Intersection Type๋ ์ธ์  ์ฌ์ฉํ ๊น?

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
        console.log("์๊ฐ ์ค");
    } ,
    word() {
        console.log("์๋ฌด ์ค"); 
    } ,
    study() {
        console.log("๊ณต๋ถ ์ค");
    } 
}
```

Intersection Type์ ๊ธฐ์กด ํ์์ ๋์ฒดํ์ง ์์ผ๋ฉด์ ๊ธฐ์กด ํ์์ ์๋ก์ด ํ๋๋ฅผ ์ถ๊ฐํ๊ณ  ์ถ์ ๋ ์ฌ์ฉ โ ํ์ฅํ๊ณ  ์ถ์ ๋ ์ฌ์ฉ ๊ธฐ์กด์ Human & Developer ํ์์ elice์ student ํ์์ ์ถ๊ฐํด ๊ธฐ์กด ํ์์ ๋ณ๊ฒฝํ์ง ์๊ณ  ํ์ฅ ๊ฐ๋ฅ

### ๐ Intersection Type ์ฃผ์ํ  ์  : ๊ฐ ํ์์ ๊ฒน์น๋ ํ๋๊ฐ ์๋ค๋ฉด ์ด๋ป๊ฒ ๋ ๊น?

๐  ํ์์ด ๊ฐ์ ๋ : Ok

```tsx
type Developer = {
    output: string;
    developer: () => void;
}
 
type Designer = {
    output: string;
    design: () => void;
}
 
const ๊ฐ์์ด๋: Developer & Designer = {
    output: 'sth cool', // ok
    developer() {
        console.log("์๋ฌด ์ค");
    },
    design() {
        console.log("์๋ฌด ์ค");
    }
}
```

๊ฐ๋ฅ

#### ๐  ํ์์ด ๋ค๋ฅผ ๋ : Error

```tsx
type Developer = {
    output: number; // ** 
    developer: () => void;
}
 
type Designer = {
    output: string;
    design: () => void;
}
 
const ๊ฐ์์ด๋: Developer & Designer = {
    output: 'sth cool', // error
    developer() {
        console.log("์๋ฌด ์ค");
    },
    design() {
        console.log("์๋ฌด ์ค");
    }
}
```

์๋ฌ

#### ๐  ํ์์ด ํฌํจ๊ด๊ณ์ผ ๋ : Ok or Error

```tsx
type Developer = {
    output: number; // ** 
    developer: () => void;
}
 
type Designer = {
    output: string | number; // ** 
    design: () => void;
}
 
const ๊ฐ์์ด๋: Developer & Designer = {
    // output: 'sth cool', // error
    output: 1, // ok (string | number) & number ์ด๋ผ์ number type์ ok!
    developer() {
        console.log("์๋ฌด ์ค");
    },
    design() {
        console.log("์๋ฌด ์ค");
    }
}
```

(string | number) & number์ด๋ผ์ number type์ ok!
