
##
```java
class Parent {
    static void hello() {
        System.out.println("Hello from Parent");
    }
}

class Child extends Parent {
    static void hello() {
        System.out.println("Hello from Child");
    }
}

public class Test {
    public static void main(String[] args) {
        Parent p = new Child();
        p.hello(); // 출력: Hello from Parent (※ Child 아님!)
    }
}
```
- 왜 Child.hello()가 호출되지 않았을까?
- 변수 p의 컴파일타임 타입이 Parent이기 때문.
- static 메서드는 객체가 아닌 클래스의 이름을 기준으로 결정


##
- ParentㆍMethod
- ParentMethodㆍChildMethod
- ✅InstanceMethodㆍInstanceMethod
- ❌InstanceMethodㆍStaticMethod
  - static method cannot hide the instance method
- ❌StaticMethodㆍInstanceMethod
  - instance method cannot override the static method
- ✅StaticMethodㆍStaticMethod


다시정의
- ✅OverRiding
- ✅Hiding