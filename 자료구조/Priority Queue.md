# Priority Queue

key, value의 쌍으로 입력이 주어지며 key는 우선순위를 나타낸다.

##### 주요 함수

- insert(e) : 원소 e를 pq에 삽입
- removeMin() : pq 내 가장 key값이 작은 값을 삭제
- min() : pq 내 가장 key값이 작은 값을 반환
- size(), empty()

##### 발생 가능한 예외

- 비어 있는 stack에서 pop() 또는 top()을 호출했을 때 예외 발생

##### 사용 예시

- 우선순위가 있는 대기 리스트
- 경매

**Priority Queue를 이용한 정렬**

1. 각 원소를 pq에 삽입

2. removeMin을 사용해 정렬된 순서대로 원소를 pq에서 제거

pq는 구현 방법에 따라 수행 시간이 다르다.