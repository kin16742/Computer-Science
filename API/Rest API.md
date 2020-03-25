# REST API

```
REST(Representational State Transfer)는 월드 와이드 웹과 같은 분산 하이퍼미디어 시스템을 위한 소프트웨어 아키텍처의 한 형식이다. 이 용어는 로이 필딩(Roy Fielding)의 2000년 박사학위 논문에서 소개되었다. 필딩은 HTTP의 주요 저자 중 한 사람이다. 이 개념은 네트워킹 문화에 널리 퍼졌다.													-위키백과-
```

### REST란?

HTTP를 기반으로 필요한 자원(DBMS, 이미지, 문서, 파일, 서비스를 모두 포함)에 접근하는 방식

이를 사용해 구현한 API를 REST API라고 한다.

각종 REST API는 인터넷을 통해 제공된다. 

#### REST의 특징

1. Uniform (유니폼 인터페이스) : URI로 지정한 리소스에 대한 조작을 통일되고 한정적으로 수행
2. Stateless (무상태성) : 작업을 위한 상태정보를 따로 저장/관리하지 않는다.
3. Cacheable : HTTP의 캐싱 기능을 적용할 수 있다.
4. Self-descriptiveness (자체 표현 구조) : REST API 메시지만 보고도 이를 이해할 수 있는 구조
5. Client-Server 구조 : 클라이언트와 서버에서 구현할 내용이 확실히 구분되어 개발할 내용이 명확해진다.
6. 계층형 구조 : 다중 계층으로 구성될 수 있어 보안, 로드 밸런싱, 암호화 계층을 추가해 구조상 유연성을 둘 수 있다.

#### REST의 속성

1. 서버의 모든 resource는 클라이언트가 바로 접근할 수 있는 고유 URI가 존재한다.

2. 모든 request는 클라이언트가 요청할 때마다 필요한 정보를 주기 때문에 서버에서 세션 정보를 보관할 필요가 없다.           

   -> 서비스 자유도가 높아지고 아키텍쳐 적응이 유연하다.

3. HTTP method를 사용한다.

   -> GET, POST, PUT, DELETE 의 4개 method로 접근되어야 한다.

4. 서비스 내 하나의 resource가 주변 연관된 resource들과 연결되어 표현되어야 한다.

#### REST 구성요소

1. Resource

   - URI(Uniform Resource Identifier)를 통해 자원에 접근한다.
   - '/' 구분자로 계층 관계를 나타낸다.        -> 따라서 마지막 문자로 '/'를 포함하지 않는다.

2. Method

   - GET : resource 조회, 자세한 정보를 가져온다
   - POST : resource 생성
   - PUT : resource 수정
   - DELETE : resource 삭제

3. Message

   - 구성요소

     - HTTP header : Body에 어떤 포맷으로 데이터가 담겼는지 정의한다. (JSON/XML/사용자 정의 포맷)

     - Body : resource 정보를 전달한다.

     - 응답 상태 코드 : 요청에 대한 응답 코드

       ![응답 상태 코드](https://miro.medium.com/max/1384/1*DLledx0g81-xbyo0KJHjyg.png)

#### REST의 장/단점

##### 장점

1. 언어와 플랫폼과 독립적이다.
2. 다른 통신방식보다 개발이 쉽고 단순하다.
3. 지원하는 프레임워크나 언어 등 도구들이 없어도 구현이 가능하다.
4. 기존 웹 인프라를 사용 가능하다. (HTTP를 그대로 사용하기 때문)

##### 단점

1. HTTP 프로토콜만 사용이 가능하다.
2. p2p 통신 모델을 가정했기 때문에 둘 이상을 대상으로 하는 분산환경에는 유용하지 않다.
3. 보안, 정책 등에 대한 표준이 없어 관리가 어렵고, 이를 고려할 시 설계/구현이 어렵다.



​	출처 : https://medium.com/@dydrlaks/rest-api-3e424716bab

​		       https://meetup.toast.com/posts/92