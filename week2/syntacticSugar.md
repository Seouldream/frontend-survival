# ๐ Syntactic sugar

Syntatic Sugar๋ ์ฝ๋๋ฅผ ๋์ฑ ๊ฐ๊ฒฐํ๊ณ , ๋ชํํ๊ฒ ์์ฑํจ์ผ๋ก์จ ๊ฐ๋์ฑ๊ณผ ์๋ฏธ ์ ๋ฌ๋ ฅ์ ๋์ด๋ ๊ธฐ๋ฒ์๋๋ค.

### Syntactic sugar ๋ถ์กฑ ์ฝ๋

```java
int a = 10;
int b = 20;
int res;
// if~else ๊ตฌ๋ฌธ ํ์ฉ ์
if (a > b) {
    res = a + b;
    } else {
    res = a - b;
}
System.out.println(res);
```

### Sugar ์ฝ๋

```java
int a = 10;
int b = 20;
int res;
// ์ผํญ์ฐ์ฐ์ ํ์ฉ
res = a>b ? a+b : a-b;
System.out.println(res);
```
