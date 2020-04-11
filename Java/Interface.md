# Interface

추상 메서드의 모음으로 어떠한 인터페이스를 사용할 때에는 인터페이스 내의 모든 함수를 구현해야만 한다.

상속은 설계 이후 변화가 없는 곳에서 사용해야 한다. 반면, 인터페이스를 사용하면 설계 이후에도 기능을 변화하는데 있어 상속을 사용하는 것보다 용이하다.

#### 역할

- 개발자 사이의 코드 규약을 정한다.
- 여러 구현체에서 공통적인 부분을 추상화한다. ( 다형성 )

#### 사용

```java
public interface Animal{
    void feed();
}
```

```java
public class Dog implements Animal{
    @Override
    public void feed(){ ... }
}
```

- 위와 같이 implements를 사용해 인터페이스를 사용할 수 있고, 인터페이스 내의 모든 함수를 구현한다.
- 인터페이스 내의 메서드는 기본적으로 public 메서드가 된다.
- 인터페이스 내에 필드 변수를 선언할 때는 public static final로 선언해야 한다.
- 인터페이스 내에 private 메서드를 구현한다면, 인터페이스 내에서 메서드 내용을 구현해야 하며, 인터페이스 밖에서는 사용할 수 없다.
- 인터페이스 또한 상속이 가능하다.

```java
public interface A{
    ...
}
public interface B extends A{
    ...
}
```

- 인터페이스 내에서 **default** 메서드를 구현했을 경우
  - 인터페이스를 사용하는 클래스에서 default 함수를 사용할 수 있다.
  - 인터페이스를 사용하는 클래스에서 default 함수를 Override할 수 있다.