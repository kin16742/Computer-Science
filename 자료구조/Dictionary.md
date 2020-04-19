# Dictionary

key, element의 쌍으로 값이 주어진다.

##### 주요 함수

- find(k) : k라는 entry가 존재한다면, 그에 대한 iterator를 반환한다.

  ```pseudocode
  Algorithm find(k)		
  for each p in [S.begin(), S.end()) do		
  	if p.key() = k  then		
  		return p
  ```

- put(k, o) : k라는 entry에 o를 삽입 후 iterator를 반환한다.

  ```pseudocode
  Algorithm put(k, v)		
  Create a new entry e = (k, v)	
  p = S.insertBack(e)
  return p
  ```

- erase(k) : k라는 entry를 삭제한다.

  ```pseudocode
  Algorithm erase(k):		
  for each p in [S.begin(), S.end()) do
  	if p.key() = k then		
  		S.erase(p)
  
  ```

- size(), empty()

##### 사용 예시

- 용어 정의
- 신용카드 승인
- DNS mapping

**List-based Dictionary**

- 각 항목을 임의 순서대로 list에 저장
- put(k,o) : O(1)
- find(k), erase(k) : O(n)

##### Search Table

- 정렬된 배열을 사용해 구현한 Dictionary이다.
- 배열은 key값을 기준으로 정렬
- 값의 개수가 적을 때 유효하다.
- find(k) : O(logn) -> binary search
- put(k,o) : O(n)
- erase(k) : O(n)