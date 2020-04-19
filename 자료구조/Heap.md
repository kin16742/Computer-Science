# Heap

heap은 key가 저장된 노드들로 이루어진 이진 트리이며 다음의 두 속성을 만족시켜야 한다.

- 모든 노드는 자신의 부모 노드보다 key값의 우선순위가 낮다

- complete binary tree이어야 한다.
- heap의 마지막 노드는 maximum depth의 가장 오른쪽 노드이다.

##### 사용 예시

- priority queue를 구현할 때 쓰일 수 있다.

##### Heap Insertion

1. 새로운 노드가 들어갈 자리를 찾는다.
2. 자리에 새로운 노드를 삽입한다.
3. **Upheap**
   - 삽입된 노드에서 위쪽 경로를 따라 heap의 속성에 맞도록 순서를 복원한다.
   - 새로운 노드의 key값인 k 이하의 key값을 가진 노드나 root에 도달하면 종료된다.
   - heap의 높이는 O(logn)이므로 upheap도 O(logn)에 수행된다.

##### Heap Removal

1. root를 마지막 노드와 교체
2. 마지막 노드 제거
3. **Downheap**
   - root로부터 아래쪽 경로를 따라 heap의 속성에 맞도록 순서를 복원한다.
   - root의 key값인 k 이상의 자식 노드를 가진 노드에 도달하거나 leaf 노드에 도달하면 종료된다.
   - heap의 높이는 O(logn)이므로 upheap도 O(logn)에 수행된다.

##### Priority Queue (Heap) Performance

- 사용 공간 : O(n)
- insert, remove : O(logn)
- size, empty, min : O(1)
- Heap Sort : O(nlogn)