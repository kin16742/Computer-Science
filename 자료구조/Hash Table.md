# Hash Table

해시 함수를 통해 특정 key를 정수에 mapping한다.

해시 함수 h를 통해 해시 값 h(x)를 얻는다.

##### Hash Function

- Hash Code : key -> integer
- Compression Function : integer -> [0, N - 1] (division, multiply, add ...)

##### Collision Handling

- 같은 인덱스에 여러 요소가 매핑될 때 충돌 발생
- Separate Chaining : 각 인덱스가 list를 가리키도록 한다.

- Open Addressing : 충돌한 항목을 다른 인덱스에 배치
- Linear Probing : 충돌 항목을 환형 배열의 사용 가능한 다음 인덱스에 배치, 검색된 각 인덱스를 probe라 칭한다.
  - 충돌해 배치된 부분이 뭉치도록 해 probe 시퀀스가 길어진다.

- Double Hashing : 두 개의 해시 함수 사용

##### 사용 예시

- database
- compiler
- browser 캐시

##### Performance

- insert, remove : O(n) -> 모든 키가 충돌할 때
- Load Factor가 성능에 영향을 미친다.
- dictionary ADT operation : O(1)