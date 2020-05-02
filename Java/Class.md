# Class

java에서는 어떤 programming이든 class에 속해 있다.

class를 사용해 객체를 생성할 수 있다.

```java
public class Animal{
    String name;
    Animal(){}
    public void eat(){}
}

Animal cat = new Animal()
```

위와 같이 Animal이라는 class의 cat 객체를 생성 (cat은 animal의 인스턴스)

#### 객체 변수

객체 변수는 class 내에 선언된 변수를 의미 (String name)

객체 변수에 접근하기 위해서는 (객체).(객체 변수) 와 같이 . 연산자를 이용해야 한다. (cat.name)

서로 다른 객체와 객체 변수를 공유하지 않는다.

#### 메소드

클래스 내에 구현된 함수를 의미한다. (public void eat())

객체 변수에 접근이 가능하며 객체 변수와 마찬가지로 . 연산자를 이용해야 한다. (cat.eat())

#### 생성자

객체가 new 키워드로 인해 생성될 때 호출되는 메소드이다.

메소드의 인자를 다르게 해  생성자를 오버로딩할 수 있다.

생성자 메소드의 이름은 클래스명과 동일해야 하며 return type을 지정하지 않는다.

생성자 메소드를 정의하지 않는다면 모두 null값으로 생성되는 default 생성자 메소드가 실행된다.