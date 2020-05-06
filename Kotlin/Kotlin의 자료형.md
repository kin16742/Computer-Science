# Kotlin의 자료형

### 변수

- val (value) - 불변형(초기화되면 수정할 수 없다.)
- var (variable) - 가변형

### 변수 선언

```kotlin
val username: String = "kildong"
```

[선언 키워드] [변수이름] [자료형] [값]

값의 자료형이 추론 가능할 때는 자료형을 생략할 수 있다.

**변수 이름 지을때 주의사항**

- 변수 이름은 123abc와 같이 숫자로 시작하면 안 됩니다.
- 변수 이름에는 while, if와 같이 코틀린에서 사용되는 키워드는 사용할 수 없습니다.
- 변수 이름은 의미 있는 단어를 사용하여 만드는 것이 좋습니다.
- 여러 단어를 사용하여 변수 이름을 지을 경우 카멜 표기법(Camel Expression)을 사용하세요.

### 자료형

- 정수형

  - 부호 있는 정수 자료형

    | 자료형 | 크기  | 범위             |
    | ------ | ----- | ---------------- |
    | Long   | 8byte | -2^63 ~ 2^63 - 1 |
    | Int    | 4byte | -2^31 ~ 2^31 - 1 |
    | Short  | 2byte | -2^15 ~ 2^15 - 1 |
    | Byte   | 1byte | -2^7 ~ 2^7  - 1  |

  - 부호 없는 정수 자료형

    | 자료형 | 크기  | 범위         |
    | ------ | ----- | ------------ |
    | ULong  | 8byte | 0 ~ 2^64 - 1 |
    | UInt   | 4byte | 0 ~ 2^32 - 1 |
    | UShort | 2byte | 0 ~ 2^16 - 1 |
    | UByte  | 1byte | 0 ~ 2^8  - 1 |

  - 사용 예시

    1. 자료형 생략

       ```kotlin
       val num1 = 127 // Int형으로 추론
       val num2 = -123123 // Int형으로 추론
       val num3 = 123124123 // Int형으로 추론
       val num4 = 1231312312312312312 // Long형으로 추론
       ```

    2. 접미사 / 접두사

       ```kotlin
       val exp1 = 123 // Int형으로 추론
       val exp2 = 12L // 접미사 L을 사용해 Long형으로 추론
       val exp3 = 0x0F // 0x를 사용해 16진표기가 사용된 Int형으로 추론
       val exp4 = 0b00001011 // 0b를 이용해 2진 표기가 사용된 Int형으로 추론
       ```

    3. 작은 값의 사용

       ```kotlin
       val exp1: Byte = 127 // 자료형을 명시해 사용
       val exp2 = 3232 // 자료형 지정 안하면 Short 범위여도 Int로 추론
       val exp3: Short = 3232 // 자료형 명시
       ```

    4. 부호 없는 정수 자료형

       ```kotlin
       val uint: UInt = 153u
       val ushort: UShort = 123u
       val ulong: ULong = 123123123uL
       val ubyte: UByte = 255u
       ```

    5. 큰 수를 읽기 쉽게 하는법

       ```kotlin
       val number = 1_000_000
       val card = 1234_1234_1234_1234L
       val hexVal = 0xAB_CD_EF_12
       val bytes = 0b1101_0010
       ```

- 실수형

  | 자료형 | 크기  | 범위                |
  | ------ | ----- | ------------------- |
  | Double | 8byte | 4.9E-324 ~ 1.7E+308 |
  | Float  | 4byte | 1.4E-45 ~ 3.4E+38   |

  ​											3.14 x 10^16 = 3.14E+16

- 논리형

  | 자료형  | 크기 | 범위        |
  | ------- | ---- | ----------- |
  | Boolean | 1bit | true, false |

- 문자형

  | 자료형 | 크기  | 범위     |
  | ------ | ----- | -------- |
  | Char   | 2byte | 0~2^15-1 |

- 문자열
  - String으로 선언되며 String pool 이라는 공간에 구성된다.