# Kotlin 반복문

#### for문

```kotlin
for (요소 변수 in 컬렉션 또는 범위){
    내용
}
```

```kotlin
for(num in 1..5) print(num)
```

kotlin의 반복문은 기본적으로 요소 변수가 증가하는 방식으로, 감소하도록 하기 위해서는 downTo를 사용해야 한다.

```kotlin
for(num in 5 downTo 1) print(num)
```

필요한 단계 증가 - step

```kotlin
for(num in 1..5 step 2) print(num) // 1 3 5
```

#### while문

```kotlin
while(조건식){ // 조건식이 true -> 반복
    내용
}
```

```kotlin
while(true){
    ... // 무한반복
}
```

#### do-while문

```kotlin
do{
    내용 // 우선 한 번 실행하고, 조건식이 true면 계속 반복
}while(조건식)
```

