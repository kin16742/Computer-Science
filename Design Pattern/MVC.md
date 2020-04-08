# MVC

MVC란 Model View Controller의 약자로 에플리케이션을 세가지의 역할로 구분한 개발 방법론이다. 

아래의 그림처럼 사용자가 Controller를 조작하면 Controller는 Model을 통해서 데이터를 가져오고 그 정보를 바탕으로 시각적인 표현을 담당하는 View를 제어해서 사용자에게 전달하게 된다. 

![](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/327/1262.png)

**Controller** : 사용자가 접근 한 URL에 따라 요청에 맞는 데이터를 Model에 요청, View에 반영해 사용자에게 응답한다.

**Model** : 사용자에게 보이지 않는 데이터, 데이터베이스, 알고리즘 등의 로직

**View** : 사용자에게 보여지는 클라이언트 측 코드를 모아놓은 것

#### MVC 동작

1. uses - User는 특정 URL에 접근
2. manipulates - Controller는 Model에 사용자의 요청을 전달
3. updates - Controller가 Model의 반환 결과를 View에 반영
4. sees - 데이터가 반영된 View를 User가 확인



references:

https://opentutorials.org/
