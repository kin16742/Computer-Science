# Kotlin null

코틀린의 변수 선언은 기본적으로 NotNull이지만 Nullable을 표현할 수 있다.

**null이 가능하도록 선언하는 방법**

```kotlin
val a: Int? = null
var b: String? = null
```

**not null 단정 기호**

접근하려는 변수가 null값을 가졌더라도 컴파일러가 오류를 무시하게 함

'!!' 키워드로 사용

```kotlin
println("length : ${str1!!.length}")
```

**Safe-call**

null pointer exception이 발생할 수 있는 곳에 '?' 키워드를 통해 안전하게 호출

```kotlin
println("length : ${str1?.length}")
```

**elvis 연산자**

if else 문과 동일하게 작동한다

```kotlin
val str1 = "hello"
val len = str1?.length ?: -1
```

