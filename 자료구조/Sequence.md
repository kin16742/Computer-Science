# Sequence

vector와 list의 통합적인 추상 자료형

Rank 또는 Position으로 접근한다.

##### 주요 함수

- Vector 기반
  - elemAtRank(r) : 인덱스 r 위치의 원소 반환
  - replaceAtRank(r, o) : 인덱스 r 위치의 원소를 o로 교체
  - insertAtRank(r, o) : 인덱스 r 위치에 원소 o를 삽입
  - removeAtRank(r) : 인덱스 r 위치의 원소 삭제
- List 기반
  - first(), last() : 맨 앞/뒤 원소 반환
  - before(p), after(p) : p 위치의 앞/뒤 원소 반환
  - replaceElement(p, o) : p 위치 원소를 o로 교체
  - swapElements(p, q) : p, q 위치 원소를 서로 교체
  - insertBefore(p, o), insertAfter(p, o) : p 위치의 앞/뒤에 원소 o를 삽입
  - insertFirst(o), insertLast(o) :  맨 앞/뒤에 원소 o를 반환
  - remove(p) : p 위치의 원소 삭제
- 그 외
  - atRank(r) : 인덱스 r을 position p로 변환
  - rankOf(p) : position p를 인덱스 r로 변환

##### 사용 예시

- stack, queue, vector, list 등의 대체용
- 데이터베이스

##### Performance

- 사용 공간 : O(n)

- Array-based, List-based 비교

  | 함수                         | Array | List  |
  | :--------------------------- | :---: | :---: |
  | size,  isEmpty               |   1   |   1   |
  | atRank,  rankOf, elemAtRank  |   1   | **n** |
  | first,  last, before, after  |   1   |   1   |
  | replaceElement, swapElements |   1   |   1   |
  | replaceAtRank                |   1   | **n** |
  | insertAtRank,  removeAtRank  | **n** | **n** |
  | insertFirst,  insertLast     |   1   |   1   |
  | insertAfter,  insertBefore   | **n** |   1   |
  | remove                       | **n** |   1   |