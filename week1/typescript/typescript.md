# π£ 2. **TypeScript**

## TypeScript: μ μ  νμ κ²μ¬μ (TypeScript: A Static Type Checker)

JavaScriptκ° κ°μ§ λ¨μ μ κ·Ήλ³΅νκΈ° μν΄ λνλ μΈμ΄.

νλ‘κ·Έλ¨μ μ€νμν€μ§ μμΌλ©΄μ μ½λμ μ€λ₯λ₯Ό κ²μΆνλ κ²μ μ μ  κ²μ¬λΌκ³  νλλ° νμμ€ν¬λ¦½νΈλ μ΄λ€ κ²μ΄ μ€λ₯μΈμ§μ μ΄λ€ κ²μ΄ μ°μ° λλ κ°μ κΈ°μΈνμ§ μμμ μ νλ κ²μ΄ μ μ  νμ κ²μ¬λ₯Ό κΈ°λ°μΌλ‘ μ€λ₯λ₯Ό μ°Ύμμ€λ€.

ex) μλ° μ€ν¬λ¦½νΈλ λμΌ μ°μ°μλ (==) μΈμλ₯Ό κ°μ λ‘ λ³ννμ¬(coerces), μκΈ°μΉ μμ λμμ μ λ°νκ±°λ μ‘΄μ¬νμ§ μλ νλ‘νΌν°μ μ κ·Όμ νμ©νλ€.


## 1. νμ μ§μ 
```tsx
let name: string;
let age: number;

name = 'νκΈΈλ';
age = 13;

name = 13;
age = 'νκΈΈλ';

let human: {
  name: string;
  age: number;
};

human = { name: 'νκΈΈλ', age: 13 };
```

## 2. νμκ³Ό μΈν°νμ΄μ€μ μ°¨μ΄μ 

νμκ³Ό μΈν°νμ΄μ€λ λ§€μ° μ μ¬νλ©°, λλΆλΆμ κ²½μ° λ μ€ νλλ₯Ό μμ λ‘­κ² μ ννμ¬ μ¬μ©ν  μ μλ€. interfaceκ° κ°μ§λ λλΆλΆμ κΈ°λ₯μ typeμμλ λμΌνκ² μ¬μ© κ°λ₯νλ€. 

> μ΄ λμ κ°μ₯ ν΅μ¬μ μΈ μ°¨μ΄λ, νμμ μ νλ‘νΌν°λ₯Ό μΆκ°νλλ‘ κ°λ°©λ  μ μλ λ°λ©΄, μΈν°νμ΄μ€μ κ²½μ° ν­μ νμ₯λ  μ μλ€λ μ μ΄λ€.

### μΈν°νμ΄μ€

μΈν°νμ΄μ€ νμ₯νκΈ°
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

κΈ°μ‘΄μ μΈν°νμ΄μ€μ μ νλλ₯Ό μΆκ°νκΈ°

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

### νμ

κ΅μ§ν©μ ν΅νμ¬ νμ νμ₯νκΈ°

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
