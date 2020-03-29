# AAC - Lifecycle

수명 주기 인식 구성요소는 Activity, Fragment처럼 다른 구성요소의 수명 주기 상태 변경에 따라 작업을 실행한다.

대부분의 Android 앱 구성요소에는 수명 주기가 연결되어 있다. 수명 주기를 준수하지 않으면 메모리 누출 또는 앱의 비정상적인 종료가 발생할 수 있다. 

<hr>

### Lifecycle

Lifecycle은 Activity, Fragment의 수명 주기 상태 정보를 포함하며, 다른 개체가 이 상태를 볼 수 있게 해주는 클래스이다.

##### 구성 ( Activity )

![Activity Lifecycle Events, States](https://developer.android.com/images/topic/libraries/architecture/lifecycle-states.svg)

- **이벤트** : Framework 및 Lifecycle 클래스에서 전달되는 수명 주기 이벤트
  - ON_CREATE   ( INITIALIZED -> CREATED )
  - ON_START   ( CREATED -> STARTED )
  - ON_RESUME   ( STARTED -> RESUMED )
  - ON_PAUSE   ( RESUMED -> STARTED )
  - ON_STOP ( STARTED -> CREATED )
  - ON_DESTROY ( CREATED -> DESTROYED )
- **상태** : Lifecycle 개체가 추적한 구성요소의 현재 상태
  - INITIALIZED : 초기 상태
  - DESTROYED : dead 상태
  - CREATED : Activity가 생성됨
  - STARTED : Activity가 시작됨 ( foreground에 보낼 준비가 됨 )
  - RESUMED : Activity가 재개됨 ( foreground에 표시됨 )



references : https://developer.android.com/topic/libraries/architecture/lifecycle#lco