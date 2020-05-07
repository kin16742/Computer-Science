# Kotlin 제어문

#### if문, if-else문

```kotlin
if(조건식){
    ...
}
else{
    ...
}
```

```kotlin
val a = 12
val b = 7
val max = if (a > b){
    println("a")
    a	// 마지막 식인 a가 반환되어 할당된다.
}
else{
    println("b")
    b	// 마지막 식인 b가 반환되어 할당된다.
}
```

#### 범위 연산자

```kotlin
n in 0..999
[변수명] in [시작값]..[마지막값]
```

#### when문

switch-case 문을 간단하게 쓸 수 있다.

```kotlin
when(x){
    1 -> print("1")
    2 -> print("2")
    else -> print("없음")
}
```

```kotlin
when(인자){
    인자에 일치하는 값 혹은 표현식 -> 수행할 문장
    인자에 일치하는 범위 -> 수행할 문장
    ...
    else -> 수행할 문장
}
```

여러 조건을 한번에 볼 때

```kotlin
when(x){
    1,2 -> print("숫자")
    else -> ...
}
```

in 연산자 사용

```kotlin
when(x){
    in 1..10 -> ~~~~
    !in 10..20 -> ~~~
    else -> ~~~
}
```

is 키워드 사용

```kotlin
var res = when(str){
    is String -> "문자열입니다"
    else -> "아닙니다."
}
```

인자 없이 사용

```kotlin
var grade: Char = 'a'
when{
    num >= 10 -> grade = 'b'
    num in 5..9 -> grade = 'c'
    num < 5 -> grade = 'd'
}
```

