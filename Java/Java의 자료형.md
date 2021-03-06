# Java의 자료형

### 1. 기본형 - Primitive Type

**분류**

```
Boolean Type 참/거짓 - boolean
Integer Type 정수 - byte, short, int, long
Floating Point Type 실수 - float, double
Character Type 문자 - char
```

**특징**

```
반드시 사용하기 전에 선언되어야 합니다.
OS에 따라 자료형의 길이가 변하지 않습니다.
비객체 타입입니다. 따라서 null 값을 가질 수 없습니다.
```

**변수명 작명 규칙**

```
대소문자를 구분한다.
변수의 이름은 숫자로 시작할 수 없다.
$ 과 _ 이외의 특수문자는 사용할 수 없다.
키워드 (지정된 예약어)는 변수의 이름으로 사용할 수 없다.
```

**크기 및 범위**

| Type    | Bits   | Range                                               |
| :------ | :----- | :-------------------------------------------------- |
| byte    | 8bits  | -2^7 ~ 2^7 - 1                                      |
| short   | 16bits | -2^15 ~ 2^15 - 1                                    |
| int     | 32bits | -2^31 ~ 2^31-1                                      |
| long    | 64bits | -2^63 ~ 2^63-1                                      |
| float   | 32bits | 1.40239846E-45f ~ 3.40282347E+38f                   |
| double  | 64bits | 4.94065645841246544E-324 ~ 1.79769313486231570E+308 |
| char    | 16bits | \u0000 ~ \uffff (0 ~ 2^15-1)                        |
| boolean | 1bit   | true, false                                         |

### 2. 참조형 - Reference Type

쉽게 생각해서 기본형이 아닌 경우 참조형이라고 볼 수 있다

기본적으로 java.lang.Object를 상속 받으면 참조형이 된다.

기본 자료형과 가장 큰 차이는 객체를 생성할 때 new를 사용한다는 것 ( string 제외 )

#### Class

생성자, 메서드, 변수로 구성되는 객체

```java
public class 클래스명 {
	// 변수
	
    // 생성자
    클래스명(){
        // 변수 초기화
    }

	// 메서드
	public static void main(String[] args){
    // 프로그램 시작 시점
    }
}
```

객체를 생성해 객체의 주소를 참조하는 자료형

#### Interface

어떤 객체가 있고 어떤 객체가 특정한 인터페이스를 사용한다면 그 객체는 **반드시 인터페이스의  메소드들을 구현해야 한다**.

만약 인터페이스에서 강제하고 있는 메소드를 구현하지 않으면 이 에플리케이션은 실행되지 않는다.

상속은 **extends**를 사용하지만 인터페이스는 **implements**를 사용한다.

**인터페이스의 규칙**

 ```
1. 하나의 클래스가 여러개의 인터페이스를 구현 할 수 있다.
2. 인터페이스도 상속이 된다.
3. 인터페이스의 맴버는 반드시 public이다. public을 생략하면 접근 제어자 default가 되는 것이 아니라 public이 된다. 
 ```

**abstract vs interface**

인터페이스와 추상 클래스는 서로 비슷한 듯 다른 기능이다. 인터페이스는 클래스가 아닌 인터페이스라는 고유한 형태를 가지고 있는 반면 추상 클래스는 일반적인 클래스다. 따라서 추상 클래스는 여러개를 상속 받는 것이 불가능하다. 또 인터페이스는 구체적인 로직이나 상태를 가지고 있을 수 없고, 추상 클래스는 구체적인 로직이나 상태를 가지고 있을 수 있다.

#### Array

Array Object를 참조하기 위해 Array 시작값을 참조값으로 가지고 있다.