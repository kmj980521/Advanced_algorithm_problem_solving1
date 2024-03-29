
# week14
## Prob1
- 합성함수
- n개의 x = 1, 2, ..., n에 대해, f(x)의 값이 주어진다.
- 일반적으로 f^k(x)라 표기하면 f(x)를 k번 합성(composition) 호출하는 것이다.
- f^k(x)는 노드 x에서 k개의 에지를 타고 이동한 노드가 f^k(x)가 된다.
- f(x)는 x의 1대 조상, f^2(x)는 2대 조상이라고 생각하면 f^k(x)는 x의 k대 조상이 된다.

### 해결 방법
- composition_query.py

### 수행시간
- O(nlogn)


---

## Prob2
- 최선과 차선(거의 최단 경로)
- 입력으로 방향 그래프 (digraph)가 주어지면, 0번 노드 (소스 노드)에서 다른 모든 노드로 가는 두 번째로 빠른 경로의 길이를 구해 모두 더한 값을 출력.
- 두 경로를 0번 노드부터 따라가다 보면 처음으로 다른 에지가 등장하는 순간이 반드시 존재해야 한다. (아니면 두 경로가 일치할테니까)
- 0번 노드에서 특정 노드까지 최단 경로가 두 개 이상이라면 가장 짧은 경로와 두 번째로 짧은 경로 모두 길이가 같다.
- 0번 노드에서 특정 노드까지 경로 자체가 존재하지 않을 수도 있다. 그 경우에는 가장 짧은 경로와 두 번째로 짧은 경로 모두 존재하지 않는다.
- 0번 노드에서 특정 노드까지 경로가 유일하게 하나만 존재할 수도 있다. 그 경우에는 가장 짧은 경로만 존재하고 두 번째로 짧은 경로는 존재하지 않는다.

### 해결 방법
- 최단 경로를 찾고, 그 경로를 제외한 경로를 재귀로 찾는다 

### 수행시간
- O(n^2 * k)


---




