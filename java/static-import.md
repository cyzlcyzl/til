# static import
Java의 static 메소드는 `Math.abs()`, `Assertions.assertThat()` 등과 같이 인스턴스를 생성하지 않고도 메서드를 사용할 수 있는데 이를 더 쉽게 사용하게 해주는 것이 바로 `static import`다.

### 예시 1.
대표적으로 AssertJ의 Assertion 메서드를 사용할 때 아래와 같은 코드를 작성한다.
```java
Assertions.assertThat(result).isEqualto(member);
```

`static import`를 활용한다면 아래와 같이 바꿀 수 있다.

```java
import static org.assertj.core.api.Assertions.*;

{
    assertThat(result).isEqualto(member);
}
```

### 예시 2.
java.lang.Math 클래스의 메서드 사용 시
```java
double r = Math.cos(Math.PI * theta);
```

`static-import`를 활용해 아래와 같이 바꿀 수 있다.
```java
import static java.lang.Math.PI;

{
    double r = cos(PI * theta)
}
```

---
`static import`를 활용함으로써 클래스 이름을 생략해 코드가 간결해져 가독성을 높일 수 있고, 특히 Test 케이스 작성 시 자주 사용하는 AssertJ의 경우 한번 import를 해두고 계속 사용하면 된다.  

**하지만 무조건 클래스 이름을 생략한다고 좋은 건 아니다.** AssertJ의 경우처럼 static 멤버에 자주 접근해야 할 때만 사용하도록 하자. `static import`를 과도하게 사용하면 해당 static 멤버가 어떤 클래스에서 왔는지 알 수가 없어 오히려 가독성을 해칠 수 있다.

----  

> 참고  
https://docs.oracle.com/javase/1.5.0/docs/guide/language/static-import.html