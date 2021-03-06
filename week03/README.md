
# week3
## Prob1
- 목표 구간 합 찾기
- 리스트 A에 저장된 n개의 양의 정수 값과 목표 값 k가 입력으로 주어지면, A의 연속된 값의 합이 k가 되는지 여부를 판별
- A = [2, 1, 4, 5, 3, 4, 6, 2]인 경우 k = 12이면, A[2]+A[3]+A[4] = 12가 되어 합이 12가 되는 구간이 존재 

### 해결 방법
- 투 포인터 기법을 사용했다
- 두 개의 포인터가 선형적으로 탐색만 하면 되기 때문에 O(n)의 시간복잡도를 가진다 
- findSum.py

### 수행시간
-  O(n)
---

## Prob2
- 작으면서 가까운 값 찾기
- 리스트 A에 저장된 n개의 자연수 값에 대해, 각 값 A[i]의 왼쪽에 있는 A[i]보다 작은 값 중에서 A[i]에 가장 가까운 위치의 수를 찾아 리스트 B에 저장한 후 출력한다 
- 그런 값이 없다면 0을 출력한다

### 예시
- A = [2, 1, 4, 5, 3]인 경우
- A[0] = 2는 왼쪽에 값이 없으므로 0을 출력
- A[1] = 1의 왼쪽에 있는 값은 2인데 A[1]보다 크므로 0을 출력
- A[2] = 4의 왼쪽에 있는 작은 값 중에 2보다 1이 더 가깝기 때문에 1을 출력
- A[3] = 5의 왼쪽에 있는 작은 값 중에 가장 가까운 값은 A[2] = 4를 출력
- A[4] = 3의 왼쪽에 가장 처음으로 등장하는 3보다 작은 값은 A[1] = 1이므로 1을 출력

### 해결 방법
- 리스트 자료구조를 이용했고 투포인터 기법을 사용했다  
- start는 시작점, min_idx는 일종의 pointer이며 값들 중에 가장 작은 값을 저장하기 위해 사용한다
- start 기준점부터 오른쪽으로 진행을 하는데 첫 if문에서 기존의 가장 작은 값인 min_num보다 더 작은 값이 온다면 min 값을 업데이트함과 동시에 start 기준 왼쪽 값들은 자기 자신보다는 반드시 크거나 같은 값이기 때문에 다른 연산 없이 0을 append 해준다
- 그것이 아니라면 자기 위치(start)부터 거꾸로 min_idx까지(위의 if문을 거치지 않았다면 min_num은 반드시 자기 자신보다 더 작은 값이므로)탐색하며 자기 자신보다 작은 값을 찾아나간다 
- findCloseMinimumValue.py

### 수행시간
-  O(n^2)


---

## Prob3
- 구간 최소값 찾기
- 리스트 A에 저장된 n개의 정수 값에 대해, 길이가 k인 구간을 왼쪽에서 오른쪽으로 이동하면서 해당 구간에 포함된 값 중에서 최소 값을 새로운 리스트 B에 저장

### 예시
- A = [2, 1, 4, 5, 3, 4, 6, 2], k = 4인 경우.
- 첫 4개의 값 2, 1, 4, 5의 최소 값은 1
- 다음 4개의 값 1, 4, 5, 3의 최소 값은 1
- 다음 4개의 값 4, 5, 3, 4의 최소 값은 3
- 다음 4개의 값 5, 3, 4, 6의 최소 값은 3
- 다음 4개의 값 3, 4, 6, 2의 최소 값은 2가 된다
- B에는 B = [1, 1, 3, 3, 2]가 저장된다

### 해결 방법
- 리스트 자료구조를 이용했고 투포인터 기법을 사용했다.
- k는 interval로 처음 범위에 대해서 min 값을 구한다(일종의 바닥조건) 
- k번째부터 (k=4면 0~3번째 인덱스에서 min 값을 구하고 다음 인덱스인 4부터 시작) n까지 반복문을 돈다.
- 첫 if문은 i-k는 이제 interval을 옮겨가는데 왼쪽에서 제외되려는 값이 min_num이면 새로운 범위에 대해서 min 값을 구하고 B에 append를 한다.
- else 문에서 즉 min값이 interval 밖으로 나가지 않는다면 새로 들어오는 값 A[i]가 min값 보다 작은지 비교해 작다면 min값을 업데이트 시키고 그 값을 B에 append 시킨다.
- 만약 새로 들어오는 값이 min값 보다 크다면 기존의 min 값을append 해준다.
- findIntervalMinimumValue.py

### 수행시간
-  O(n^2)


