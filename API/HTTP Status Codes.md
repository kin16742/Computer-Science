# HTTP Status Codes

```
모든 HTTP 응답 코드는 5개의 클래스(분류)로 구분된다.
상태 코드의 첫 번째 숫자는 응답의 클래스를 정의한다.
마지막 두 자리는 클래스나 분류 역할을 하지 않는다.
```

#### 1xx (Informational Category)

- 요청을 받았으며 프로세스를 계속한다. (Continue, Switching Protocols, Processing)

#### 2xx (Success Category)

- 요청을 성공적으로 받았으며 인식했고 수용하였다.

- 200 OK
  - 성공적으로 클라이언트의 요청을 처리했을 때.
  - 서버가 요청한 페이지를 제공했다는 의미로 쓰인다. 
- 201 Created
  - 새로운 resource가 데이터베이스 등에 작성되었을 때. (POST, PUT)
  - 서버에서 요청을 즉시 처리할 수 없을 경우에는 202 코드로 응답한다.
- 202 Accepted
  - 요청이 처리를 위해 승인되었지만 처리가 완료되지 않았을 때.
  - 결국에 요청이 처리가 되지 않을수도 있다.
- 204 No Content
  - 클라이언트의 요청을 성공적으로 처리했지만 response로 데이터를 제공하지 않을 때.

#### 3xx (Redirection Category)

- 요청 완료를 위해 추가 작업 조치가 필요하다.

- 301 Moved Permanently
  - 요청 resource에 영구적인 URI가 할당되었을 때
  - 이후의 참조는 반환된 URI를 사용하여야 함
- 302 Found
  - 요청된 리소스에는 새로운 URI가 지정되어 있기 때문에, 이후로는 새 URI를 사용해야 한 다는 것을 나타냄
  - 경우에 따라 Redirection이 변경될 수 있다.
- 303 See Other
  - 요청에 대한 리소스는 다른 URI에 있기 때문에 GET 메서드를 사용해서 얻어야 한다는 것을 나타냄
  - 302와 다른 점은 GET 메서드를 사용해야만 한다는 점
- 304 Not Modified
  - 마지막 요청 이후 resource가 수정되지 않았을 때.
  - 요청한 리소스가 마지막 요청 이후 변경된 적이 없기 때문에 기존 클라이언트의 로컬 캐시 리소스를 사용하도록 알려줌.
- 307 Temporary Redirect
  - 요청 resource가 일시적으로 다른 URI에 있을 때 임시로 페이지를 리다이렉트 함.
  - 302와 다른 점은 원래의 메서드를 그대로 사용해야만 한다는 점

#### 4xx (Client Error Category)

- 요청 문법이 잘못되었거나 요청을 처리할 수 없다.

- 400 Bad Request
  - 클라이언트 측의 요청이 잘못되었을 때
  - 도메인 오류, 누락데이터 등
- 401 Unauthorized
  - 요청에 사용자 인증이 필요할 때 (HTTP 인증 정보 필요)
- 403 Forbidden
  - 서버가 요청을 이해했지만 접근을 금지할 때
- 404 Not Found
  - 서버가 일치하는 URI를 찾지 못했을 때
- 405 Method Not Allowed
  - 특정 URI에서 허용되지 않는 메서드를 사용할 때
- 409 Conflict
  - resource의 현재 상태와 충돌이 발생해 처리할 수 없을 때
- 412 Precondition Failed
  - 요청에 포함된 전제 조건이 서버에서 충족되지 않을 때
- 415 Unsupported Media Type
  - 요청이 지원되지 않는 미디어 타입을 가져 서버가 이를 거부할 때

#### 5xx (Server Error Category)

- 서버가 명백히 유효한 요청에 대해 충족을 실패했다.
- 500 Internal Server Error
  - 서버에서 요청을 처리 중에 에러가 발생할 때
- 501 Not Implemented
  - 서버가 요청 방법을 인식하지 못했거나 그러한 기능이 없을 때



적어놓은 코드 번호 외에도 많다. Reference 참조하기

References : 

https://www.restapitutorial.com/httpstatuscodes.html

https://restfulapi.net/http-status-codes/

