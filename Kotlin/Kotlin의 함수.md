# Kotlin의 함수

**함수의 종류**

- 최상위 함수 (main)
- 지역 함수

**함수의 선언**

```kotlin
fun sum(a: Int, b: Int): Int{
    var sum = a + b
    return sum
}
```

```kotlin
fun [함수명]\([변수 이름: 자료형, 변수 이름: 자료형 ....]): [반환값의 자료형]{
    ...
    [return 반환값]
}
```

반환값의 자료형으로 쓰이는 Unit은 아무런 형을 반환하지 않는 특수형으로, 생략이 가능하다.

**함수 간략화**

```kotlin
fun sum(a: Int, b: Int) = a + b
```

**매개변수**

- 매개변수와 인자의 차이
  - 매개변수 : 함수 정의 시의 parameter
  - 인자 : 함수 사용 시의 parameter
  - 인자로 넘겨준 값이 매개변수로 복사되어 사용된다
- 매개변수로 기본값을 넘겨줄 수 있다.