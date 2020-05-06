# MVVM

MVVM란  Model-View-ViewModel의 약자이다. 

**Model** : 사용자에게 보이지 않는 데이터, 데이터베이스, 알고리즘 등의 로직 -> View에 표시할 데이터

**View** : 사용자에게 보여지는 클라이언트 측 코드를 모아놓은 것 -> UI, 받아온 데이터를 뿌리는 일에 집중

**ViewModel** : View와 관련된 로직이 이곳에 들어간다. 데이터를 가공해 View에 뿌리기 쉬운 Model로 바꾸는 역할이다.

#### 특징

Input은 View에 직접

View와 ViewModel의 관계 : Many to One

ViewModel은 View를 참조하지 않고, View는 Model을 참조하지 않는다. (ViewModel을 통해 Model을 업데이트)

#### 동작

1. View에 input이 들어온다.

2. View가 참조하는 ViewModel에서 Binding된 객체를 찾는다.

3. ViewModel을 통해 Model을 업데이트한다.

   (View와 Model은 완벽히 분리되어있다.)

#### MVC와의 차이점

View가 필요한 데이터와 커맨드를 지원한다.

ViewModel을 View에 바인딩할 때 강력하다.

커맨드와 데이터바인딩 덕분에 View와 Controller의 관계를 끊을 수 있다.