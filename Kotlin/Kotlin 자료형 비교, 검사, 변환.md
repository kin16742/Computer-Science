# Kotlin 자료형 비교, 검사, 변환

```kotlin
val a: Int = 1
val b: Double = a // 자료형 불일치 오류 발생
```

위와 같은 오류를 해결하기 위해 변환 메소드를 사용해야 한다.

```kotlin
val b: Double = a.toDouble()
```

**변환 메소드의 종류**

- toByte, toLong, toShort, toFloat, toInt, toDouble, toChar

**자료형의 비교**

- '==' : 값만 비교하는 경우
- '===' : 값과 참조 주소를 함께 비교할 때

**스마트 캐스트**

- 구체적으로 명시되지 않은 자료형을 자동으로 변환

- 값에 따라 자료형을 결정한다.

- Number 형은 숫자를 저장하기 위한 특수한 자료형으로 스마트 캐스팅이 된다.

  ```kotlin
  var test: Number = 12.2 // Float 형으로 스마트 캐스트
  test = 12 // Int 형으로 스마트 캐스트
  test = 120L // Long 형으로 스마트 캐스트
  ```

**자료형의 검사**

- 'is' 키워드

  ```kotlin
  val num = 256
  if(num is Int) { ... }
  else if (num !is Int) { ... }
  ```

**묵시적 변환**

- 'Any' 키워드

- 자료형이 정해지지 않은 경우 언제든 필요한 자료형으로 자동 변환

  ```kotlin
  var a: Any = 1 // Int 형으로 스마트 캐스트
  a = 20L // Long 형으로 스마트 캐스트
  ```

- 사용 예시

  ```kotlin
  fun test(x: Any){
      if(x is String){...}
      if(x is Int){...}
  }
  ```

  