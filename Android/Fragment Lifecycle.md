# Fragment Lifecycle

#### Fragment란?

FragmentActivity 내의 어떤  동작 또는 사용자 인터페이스의 일부를 나타낸다

여러 개의 Fragment를 하나의 Activity에 결합하여 창이 여러 개의 UI를 빌드할 수 있다.

자체적인 수명 주기를 가지고, 자체 입력 이벤트를 수신하고, Activity 실행 중에 추가, 삭제가 가능하다.

#### Activity와의 관계

Fragment는 항상 Activity 내에서 호스팅되어야 한다.

수명주기 또한 호스트 Activity의 수명주기에 직접적으로 영향을 받는다. (Activity 소멸 -> Fragment 소멸)

#### Fragment 수명주기

![Fragment Lifecycle](https://developer.android.com/images/fragment_lifecycle.png?hl=ko)

- onAttach()
  - Fragment가 Activity에 attach될때 호출된다.
  - 인자로 context가 주어진다.
- onCreate()
  - Fragment를 생성할 때 시스템에서 이것을 호출한다.
  - Fragment가 재개되었을 때 유지하고자 하는 것(리소스)을 초기화해야 한다.
  - UI 초기화는 할 수 없다.
- onCreateView()
  - 인터페이스를 그릴 때 시스템에서 이것을 호출한다.
  - UI를 초기화해 View를 반환해야 한다.
- onActivityCreated()
  - Fragment가 onCreateView()를 마친 상태에서, 호스트 Activity가 onCreate()를 호출한 뒤 호출된다.
  - View를 변경하는 작업이 가능하다
- onStart(), onResume() - Activity와 유사
- onPause(), onStop() - Activity와 유사
  - 사용자가 Fragment를 떠난다는 것을 나타내는 첫 번째 신호이다.
  - 호스트 Activity가 아닌 다른 Activity가 foreground로 나오게 되면 호출되고 Backstack으로 들어간다.
  - 다른 Activity가 화면을 완전히 가리게 되면, onStop()을 호출
- onDestroyView() - Fragment와 관련된 View 제거되는 단계
- onDestroy() - Fragment destroy
- onDetach() - Fragment가 호스트 Activity로부터 해제될 때 호출