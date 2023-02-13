# Syntatic Sugar란?
Syntatic Sugar란 코드를 더욱 간결하고, 명확하게 작성함으로써 가독성과 의미 전달력을 높이는 기법입니다.

### Syntactic sugar 부족 코드
``` java
int a = 10;
int b = 20;
int res;
// if~else 구문 활용 예
if (a > b) {
    res = a + b;
    } else {
    res = a - b;
}
System.out.println(res);
```

### Sugar 코드
``` java
int a = 10;
int b = 20;
int res;
// 삼항연산자 활용
res = a>b ? a+b : a-b;
System.out.println(res);
```
