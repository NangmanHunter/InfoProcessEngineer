

##
형변환
- ❌변수
- ✅메소드

## this
- 클래스
- 현재 실행중인 메소드가 속한 클래스를 가리키는 예약어


## Exception
Exception
- RuntimeException
  - ArithmeticException
  - ArrayIndexOutOfBoundsException
  - NumberFormatException

```php
java.lang.Object
  └── java.lang.Throwable
        └── java.lang.Exception
              └── java.lang.RuntimeException
                    ├── ArithmeticException
                    ├── ArrayIndexOutOfBoundsException
                    ├── NumberFormatException
```

- [Exception](https://docs.oracle.com/javase/8/docs/api/java/lang/Exception.html)
- [RuntimeException](https://docs.oracle.com/javase/8/docs/api/java/lang/RuntimeException.html)


## 생성자ㆍ필드
- 부모생성자▶️✅부모필드ㆍ❌자식필드
- 자식생성자▶️✅부모필드ㆍ✅자식필드
- 자식생성자▶️✅부모필드<<✅자식필드

부모생성자
ㄴ❌자식필드
ㄴ없는경우
ㄴ컴파일에러.

자식생성자
ㄴ없는경우
ㄴ✅부모필드
ㄴ부모필드긁어다옴.

- ✅ 부모 생성자에서는 부모 클래스의 필드만 접근 가능
- ✅ 자식 생성자에서는 부모 클래스 + 자식 클래스 필드 모두 접근 가능

```java
new Child();  // 실행 순서:
→ Parent() 생성자 먼저 실행  
→ Child() 생성자 실행
```
- Parent()가 실행될 때는 아직 Child의 필드가 메모리에 존재하지 않음
- 반면, Child()가 실행될 때는 이미 Parent 부분은 모두 초기화됨
