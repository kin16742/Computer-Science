# Kotlin 흐름 제어문

#### 흐름 제어문

return : 결과값 반환, 지정된 라벨로 이동

break : 반복문의 조건식에 상관없이 반복문을 끝냄

continue : 반복문을 모두 수행하지 않고 다시 조건식으로 넘어감

#### 예외 처리문

예외

- 운영체제 문제
- 입력값 문제
- 받아들일 수 없는 연산 (0으로 나누기 등)
- 메모리 할당 실패 및 부족
- 하드웨어 문제

try-catch : 예외가 발생하면 catch 블록 실행

try-catch-finally : 예외가 발생해도 finally 블록은 항상 실행

```kotlin
try{ ... }
catch{ ... }
finally{ ... }
```

throw : 예외를 의도적으로 발생시키기

```kotlin
throw Excepton(message: String)
```

### 라벨

#### 람다식에서 라벨과 함께 return 사용하기

```kotlin
fun inlineLambda(a: Int, b: Int, out: (Int, Int) -> Unit) { // inline이 제거됨
    out(a, b)
}

fun retFunc() {
    println("start of retFunc")
    inlineLambda(13, 3) lit@{ a, b ->  // 1 람다식 블록의 시작 부분에 라벨을 지정함
        val result = a + b
        if(result > 10) return@lit // 2 라벨을 사용한 블록의 끝부분으로 반환
        println("result: $result")
    } // 3 이 부분으로 빠져나간다
    println("end of retFunc") // 4 이 부분이 실행됨 
}
```

람다식에서 라벨을 사용하지 않고 return하면 바깥 함수가 반환되는 비지역 반환이 일어난다.

#### 암묵적 라벨

라벨 이름 대신 함수명을 넣으면 같은 기능을 한다.

```kotlin
fun retFunc() {
    println("start of retFunc")
    inlineLambda(13, 3){ a, b ->  
        val result = a + b
        if(result > 10) return@inlineLambda 
        println("result: $result")
    } 
    println("end of retFunc")
}
```

#### 익명 함수의 사용

```kotlin
fun retFunc() {
    println("start of retFunc")
    inlineLambda(13, 3, fun(a, b){
        val result = a + b
        if(result > 10) return
        println("result: $result")
    })
    println("end of retFunc")
}
```

라벨을 사용하지 않아도 비지역 반환이 일어나지 않는다.

하지만, 많이 사용하게 되면 원리를 파악하기 어려울 수 있다.

#### break문과 라벨

break를 사용하면 바로 바깥 for문을 탈출하지만, 라벨을 사용하면 지정된 곳으로 탈출한다.

```kotlin
fun labelBreak() {
    println("labelBreak")
    first@ for(i in 1..5) { // break시 여기로 옴
        second@ for (j in 1..5) {
            if (j == 3) break@first
            println("i:$i, j:$j")
        }
        println("after for j")
    }
    println("after for i")
} 
```

