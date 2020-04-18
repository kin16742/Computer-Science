# Tree

계층적 구조를 나타내는 추상자료형

parent-child 관계의 노드들로 구성된다.

##### 사용 예시

- 조직도
- 파일 시스템
- 프로그래밍 환경

##### 용어

- Root : 트리의 최상위 노드
- Internal node : 적어도 하나의 자식 노드를 가진 노드
- External node : 자식 노드가 하나도 없는 노드 ( 맨 바깥쪽의 노드 )
- Ancestor : 어떤 노드의 부모 노드를 포함한 모든 상위 노드
- Depth : 특정 노드의 ancestor의 수
- Height : depth의 최대값
- Subtree : 트리의 일부분

##### 주요 함수

- integer size() : 트리 내 노드 개수 반환
- boolean empty() : 트리가 비어있는지의 여부를 반환
- position root() : root의 position값 반환
- list<position> positions() : 모든 노드의 position값 반환
- position parent() : 현재 position 기준 부모 노드의 position 반환
- list<position> children() : 현재 position 기준 모든 자식 노드의 position 반환
- boolean isRoot() : root인지의 여부를 반환
- boolean isExternal() : externel node인지의 여부를 반환

##### Preorder Traversal

구조화된 문서를 출력할 때 쓰일 수 있음

```pseudocode
Algorithm preOrder(v)
	visit(v)
    for each child w of v
		preOrder (w)
```

##### Postorder Traversal

컴퓨터 내 디렉토리 구조를 나타낼 때 쓰일 수 있음

```pseudocode
Algorithm postOrder(v)
	for each child w of v
		postOrder (w)
	visit(v)
```

##### Inorder Traversal

이진 트리를 그릴 때, 계산식을 표현할 때 사용

```pseudocode
Algorithm inOrder(v)
	if !v.isExternal()
		inOrder(v.left())
	visit(v)
	if !v.isExternal()
		inOrder(v.right())
```

##### Euler Tour Traversal

이진 트리를 순회할 때 쓰인다.

preorder, postorder, inorder를 모두 포함하는 특별한 경우

각 노드를 세 번씩 방문한다.

##### Array-Based Binary Tree

Node v는 A배열의 rank(v) 인덱스에 저장된다.

- rank(root) = 1
- parent(node)의 왼쪽 자식 노드 = rank(node) = 2 × rank(parent(node))
- parent(node)의 오른쪽 자식 노드 = rank(node) = 2 × rank(parent(node)) + 1