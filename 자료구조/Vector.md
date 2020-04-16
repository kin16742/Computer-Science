# Vector

Array List 라고도 한다.

인덱스를 사용해 원소에 접근, 원소 삽입/삭제

##### 주요 함수

- at(integer i) : vector 내 인덱스 i에 해당하는 원소 반환
- set(integer i, object o) : vector 내 인덱스 i에 해당하는 원소를 o로 대체
- insert(integer i, object o) : vector 내 인덱스 i에 원소 o를 삽입
- erase(integer i) : vector 내 인덱스 i에 해당하는 원소 삭제
- size()
- empty()

##### 발생 가능한 예외

- 잘못된 인덱스에 접근하려 할 때 예외가 발생한다.

##### 사용 예시

- 보조 데이터베이스 ( 정렬된 개체 집합 )
- 알고리즘 보조 데이터 구조

##### Array-based Queue 

- 배열이 꽉 차있을 때 원소를 삽입하면 원래의 배열을 대체한다.
  - 크기를 정해 키워야 할 때 그만큼 배열을 키운다.
  - 원래 배열 크기의 두 배로 키운다.

##### Performance

- 사용 공간 : O(n)
- at(), set(), size(), empty() : O(1)
- insert(), erase() : O(n)