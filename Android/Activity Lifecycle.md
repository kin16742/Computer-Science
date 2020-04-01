# Activity Lifecycle

사용자가 앱을 사용할 때 앱의 Activity 인스턴스는 lifecycle 안에서 서로 다른 상태를 통해 전환된다. Activity class는 상태변화를 알아차릴 수 있는 여러 콜백을 제공한다.

![Activity Lifecycle](https://developer.android.com/guide/components/images/activity_lifecycle.png)

### Callback 메서드

- onCreate()
  - Activity를 생성할 때 실행된다. (필수적으로 구현해야 함)
  - Activity 전체 lifecycle 동안 한 번만 발생해야 하는 로직을 수행한다. (Data Binding, ViewModel과의 연결, 변수 인스턴스화)
  - savedInstanceState 매개변수를 수신한다. (이전 저장 상태가 포함된 객체)
  - ON_CREATE 이벤트를 수신
  - 생성됨 상태에 머무르지 않고, 메서드가 실행되면 Activity는 시작됨 상태가 되고, onStart()와 onResume()을 연달아 호출한다.
- onStart()
  - Activity가 시작됨 상태에 들어갈 때 실행된다.
  - Activity가 사용자에게 보이게 되고, foreground에 보내 상호작용할 수 있도록 준비한다.
  - UI를 관리하는 코드를 초기화한다.
  - ON_START 이벤트를 수신
  - 시작됨 상태에 머무르지 않고 빠르게 완료되며, 완료 후에 onResume()을 호출한다.
- onResume()
  - Activity가 재개됨 상태에 들어갈 때 실행된다.
  - 앱이 사용자와 상호작용하는 상태가 된다.
  - 특정 이벤트가 발생할 때까지 이 상태에 머무른다.(다른 Activity로의 이동, 화면이 꺼지는 등)
  - 이벤트 발생 시에는 Activity는 일시정지 상태에 들어가고 onPause()를 호출한다.
- onPause()
  - Activity를 떠나는 것을 나타내는 첫 번째 신호로 호출한다. (항상 소멸되는 것은 아님)
  - Activity가 foreground에 있지 않게 되었다는 것을 의미 (특정 이벤트 발생 시, 다른 Activity 실행 중일 때 등)
  - ON_PAUSE 이벤트를 수신
  - 리소스 해제, 조정 시에는 onStop()을 사용하는 것이 좋다.
  - 데이터 저장, 네트워크 호출, 트랜잭션을 onPause()에서 실행해서는 안 된다.
- onStop()
  - Activity가 더 이상 사용자에게 표시되지 않으면 중단됨 상태에 들어가고 onStop()이 호출된다.
  - ON_STOP 이벤트를 수신
  - 이 메서드 내에서 필요하지 않은 리소스를 해제하거나 조정해야 한다.
- onDestroy()
  - Activity가 소멸되기 전에 호출된다. (Activity 완전히 종료, finish() 호출 시, 기기 회전이나 멀티 윈도우 모드 등 구성 변경으로 인해 일시적으로 Activity 소멸)
  - ON_DESTROY 이벤트를 수신
  - 이 메서드 내에서 Activity가 소멸되기 전에 필요한 것을 정리할 수 있다.
  - 이전의 콜백에서 아직 해제되지 않은 모든 리소스를 해제해야 한다.

### Activity 상태

| 종료될 가능성 | 프로세스 상태                                    | Activity 상태        |
| :------------ | :----------------------------------------------- | :------------------- |
| 최소          | 포그라운드(포커스가 있거나 포커스를 가져올 예정) | 생성됨 시작됨 재개됨 |
| 높음          | 백그라운드(포커스 상실)                          | 일시정지됨           |
| 최대          | 백그라운드(보이지 않음)                          | 정지됨               |
|               | 비어 있음                                        | 소멸됨               |



references : 

https://developer.android.com/guide/components/activities/activity-lifecycle