# stack
## 먼저 들어온 데이터가 나중에 나가는 형식 (FILO)
- 입구와 출구가 동일한 형태 ex.박스쌓기
![stack](./assets/)

- DFS 알고리즘 외에도 다양한 알고리즘에서 사용됨.

- 스택의 동작 : 삽입 + 삭제
- `append`, `pop`은 시간복잡도가 상수시간 `O(1)`이다.

- 스택의 예시
```python
stack = []
# 삽입(1) - 삽입(2) - 삽입(3) - 삽입(4) - 삭제 - 삽입(5) - 삽입(6) - 삽입(7) - 삽입(8) - 삭제()
stack.append(1)
# stack = [1]
stack.append(2)
# stack = [1, 2]
stack.append(3)
# stack = [1, 2, 3]
stack.append(4)
# stack = [1, 2, 3, 4]
stack.pop()
# stack = [1, 2, 3]
stack.append(5)
# stack = [1, 2, 3, 5]
stack.append(6)
# stack = [1, 2, 3, 5, 6]
stack.append(7)
# stack = [1, 2, 3, 5, 6, 7]
stack.append(8)
# stack = [1, 2, 3, 5, 6, 7, 8]
stack.pop()
# stack = [1, 2, 3, 5, 6, 7]

print(stack[::-1]) # 최상단 원소부터 출력
# 실행 결과 : [7, 6, 5, 3, 2, 1]

print(stack) # 최하단 원소부터 출력
# 실행 결과 : [1, 2, 3, 5, 6, 7]
```

- `C++`, `java`에서도 `stack`자료구조를 지원

# queue
## 먼저 들어온 데이터가 먼저 나가는 형식 (FIFO)
- 입구와 출구가 모두 뚤려있는 형태 ex. 터널
![queue](./assets/)

- `list`를 이용해 큐를 구현할 수는 있지만 시간복잡도가 더 높아 비효율적으로 동작할 수 있어 라이브러리를 사용
- `deque` 자료구조는 스택과 큐의 장점을 모두 합친 자료구조 
- `deque`에서 사용되는 `append`, `popleft` 모두 시간복잡도가 상수시간 `O(1)`이다.
    - `deque` 미사용시, `pop` 사용 후 데이터 정렬이 필요하므로, 시간복잡도가 `O(k)`만큼 늘어나므로 `deque`를 사용하는것을 권장.
- `python` 에서 큐를 구현시 `append`, `popleft`를 관행적으로 사용
    - `append`가 오른쪽 삽입임에도 불구하고 사용

- 큐의 예시
```python
from collections import deque
# queue 구현을 위해 deque 라이브러리 필요
queue = deque()
# 삽입(1) - 삽입(2) - 삽입(3) - 삽입(4) - 삭제 - 삽입(5) - 삽입(6) - 삽입(7) - 삽입(8) - 삭제()
queue.append(1)
# queue = [1]
queue.append(2)
# queue = [2, 1]
queue.append(3)
# queue = [3, 2, 1]
queue.append(4)
# queue = [4, 3, 2, 1]
queue.popleft()
# queue = [4, 3, 2]
queue.append(5)
# queue = [5, 4, 3, 2]
queue.append(6)
# queue = [6, 5, 4, 3, 2]
queue.append(7)
# queue = [7, 6, 5, 4, 3, 2]
queue.append(8)
# queue = [8, 7, 6, 5, 4, 3, 2]
queue.popleft()
# queue = [8, 7, 6, 5, 4, 3]

print(queue) # 먼저 들어온 순서대로 출력
# 실행 결과 : deque([3, 4, 5, 6, 7, 8])

queue.reverse() # 역순으로 바꾸기
print(queue) # 최하단 원소부터 출력
# 실행 결과 : deque([8, 7, 6, 5, 4, 3])
```
- `C++`, `java`에서도 `queue`자료구조를 지원
