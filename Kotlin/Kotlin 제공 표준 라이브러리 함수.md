# Kotlin 제공 표준 라이브러리 함수

#### let()

```kotlin
public inline fun <T, R> T.let(block: (T) -> R): R {... return block(this)}
```

T, R : 형식 매개변수 => 어떤 자료형이든 사용할 수 있도록 일반화한 문자

호출하는 객체 T를 매개변수로 받아 block에 넘겨주고 결과값인 R을 반환

let() 함수도 R을 반환

본문의 this는 객체 T를 가리키는데, 람다식 결과 부분을 그대로 반환한다는 뜻이다.

다른 메소드를 실행하거나 연산을 수행해야 하는 경우 사용

```kotlin
// let() 체이닝
var a = 1
var b = 2

a = a.let { it + 2 }.let {
    val i = it + b
    i  // 마지막 식 반환
}
println(a) //5
```

중첩 사용 시에는 it을 사용하지 않고 명시적 이름을 사용해야 한다.

```kotlin
var x = "xx"
x.let {outer ->
      outer.let{ inner ->
                print("inner is $inner outer is $outer")
               }
      }
```

반환값은 바깥쪽 람다식에만 적용된다.

**활용**

- 안드로이드 커스텀 뷰에서  Padding 값 지정

- null 검사

- null 가능성이 있는 변수 사용 시 else문이 포함된 문장 대체

  ```kotlin
  firstName?.let {print("$it $lastName")} ?: print("$lastName")
  ```

#### also()

```kotlin
public inline fun <T> T.also(block: (T) -> Unit): T { block(this); return this }
```

let() 과의 차이점

- block의 반환값이 없다.
- 객체 T 자체를 반환한다.

```kotlin
var m = 1
m = m.also{it + 3} // 4는 반환되지 못함!
println(m) // 1
```

```kotlin
data class Person(var name: String, var skills: String)
var person = Person("dd", "aa")

val a = person.let{
    it.skills = "Android"
    "success"
}
println(a) // success
val b = person.also{
    it.skills = "zz"
    "success" // 반환 x
}
println(b) // Person의 객체 b
```

#### apply()

```kotlin
public inline fun <T> T.apply(block: T.() -> Unit): T { block(); return this }
```

호출하는 객체 T를 이어지는 block으로 전달하고 객체 자체인 this를 반환

T.()와 같은 표현에서 람다식을 확장 함수로 처리

객체를 생성하면서 함께 호출해야 하는 초기화 코드에 사용할 수 있다. (ex 레이아웃 초기화)

```kotlin
fun main() {
    data class Person(var name: String, var skills : String)
    var person = Person("Kildong", "Kotlin")

    // 여기서 this는 person 객체를 가리킴
    person.apply { this.skills = "Swift" }
    println(person)

    val retrunObj = person.apply { 
        name = "Sean" // this는 생략할 수 있음
        skills = "Java" // this 없이 객체의 멤버에 여러 번 접근
    }
    println(person)
    println(retrunObj)
}
```

#### run()

```kotlin
public inline fun <R> run(block: () -> R): R  = return block()
public inline fun <T, R> T.run(block: T.() -> R): R = return block()
```

익명 함수처럼 동작하는 형태, 확장 함수 형태의 두 가지로 사용 가능

apply()와의 차이점 - 객체 자체인 this 대신 마지막 식을 반환한다

#### with()

```kotlin
public inline fun <T, R> with(receiver: T, block: T.() -> R): R  = receiver.block()
```

확장 함수 형태가 아닌, 단독으로 사용되는 함수이다.

run()과의 차이점 - 결과값을 반환하면서 동시에 receiver로 전달할 객체를 처리한다.

세이프 콜을 지원하지 않으므로 let과 같이 사용되기도 한다.

```kotlin
supportActionBar?.let {
    with(it) {
        setDisplayHomeAsUpEnabled(true)
        setHomeAsUpIndicator(R.drawable.ic_clear_white)    
    }
}
```

```kotlin
fun main() {
    data class User(var name: String, var skills : String, var email: String? = null)
    var user = User("Kildong", "default")

    val result = with(user){
        skills = "kotlin"
        email = "aaa@aaa.aaa" 
    }
    println(user) // 값이 변경된 객체 user
    println(result) // Kotlin.Unit
}
```

#### use()

```kotlin
public inline fun <T : Closeable?, R> T.use(block: (T) -> R): R 
```

특정 객체를 사용한 후 close() 등을 자동으로 호출해 닫아준다.

T의 자료형에는 닫힐 수 있는 객체를 지정해야 한다.

```kotlin
fun readFirstLine(): String{
    BufferedReader(FileReader("test.file")).use(return it.readLine())
} // test.file은 readLine() 이후 close()까지된다.
```

#### takeIf()와 takeUnless()

람다식 검사에 쓰이는 함수들

- takeIf() : 람다식이 true이면 객체 T를 반환하고 그렇지 않은 경우 null 반환
- takeUnless() : 람다식이 false이면 객체 T를 반환하고 그렇지 않은 경우 null 반환 

```kotlin
// 기존 코드
if(obj != null && obj.status)
	dothis()
// 개선 코드
if(obj?.status == true)
	dothis()
// takeIf를 사용한 개선 코드
obj?.takeIf(it.status)?.apply{dothis()}
```

```kotlin
// 입력 문자열에 키워드가 있으면 인덱스를 반환하는 함수
val input = "Kotlin"
val keyword = "in"

input.indexOf(keyword).takeIf {it >= 0} ?: error("keyword not found")
```

#### 난수 생성

kotlin.random.Random import해서 사용

```kotlin
val number = Random.nextInt(21)
```