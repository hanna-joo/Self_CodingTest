# 1. 파이썬 기초

# 2. 자료구조
## (1) 구간 합 : O(1)
## (2) 투 포인터 : O(nlogn)
## (3) 슬라이딩 윈도우 : O(n)
- 윈도우를 한 칸씩 이동하며 현재 상태 리스트 업데이트
- 슬라이딩 윈도우를 덱으로 구현하면 정렬 효과
  - `deque.append(item)`, `deque.appendleft(item)`, `deque.pop()`, `deque.popleft()`
## (4) 스택과 큐
- 스택(stack)
  - 깊이 우선 탐색(Depth First Search), 백트래킹 종류의 코딩에 효과적
- 큐(queue) 
  - 너비 우선 탐색(Breadth First Search)에서 자주 사용
- 우선순위 큐(priority queue)
  - 기본적으로 정렬 기준은 오름차순 정렬
## (5) 해시

# 3. 완전 탐색

# 4. DFS & BFS
## (1) 깊이 우선 탐색 (Depth-First Search)
- 그래프 완전 탐색 기법 중 하나
- 루트 노드에서 시작해서 다음 분기로 넘어가기 전에 해당 분기를 완벽하게 탐색하는 방식
- 방문하고 스택에 넣어놓고 나중에 넣은 것부터 처리(방문하자마자 처리)
- 후입선출, **스택** 또는 **재귀함수**로 구현
- 구현 요소 : 인접리스트, 방문리스트, 스택/재귀 함수(, 시작 노드)
  - 시작 노드 입력 
  - 시작 노드 방문 기록 있다면 dfs 종료
  - 시작 노드 방문 기록 없다면 방문 기록 후 처리
  - 해당 노드의 인접 노드 하나씩 dfs 수행
## (2) 너비 우선 탐색 (Breadth-First Search)
- 루트 노드에서 시작해서 시작 정점으로부터 인접한 노드를 먼저 탐색하는 방식
- 선입선출, **큐**로 구현
- 방문하고 큐에 넣어놓고 가장 먼저 넣은 것부터 처리
- 구현 요소 : 인접리스트, 방문리스트, 큐(, 탐색 방향, 시작 노드)
  - 시작 노드 입력
  - 시작 노드 방문 기록 후 큐에 넣기
  - 큐가 빌 때까지 반복
    - 큐에서 가장 앞 노드 추출
    - 해당 노드 처리
    - 해당 노드의 인접 노드 하나씩 방문 및 큐에 삽입
  - 문제 : bfs_230417
## (3) DFS vs BFS
- 모든 노드를 방문해야 할 때 DFS, BFS
- 각각의 경로마다 특징을 저장해야 할 때 DFS
- 두 노드 사이의 최단 거리 구해야 할 때 BFS
- 시간 복잡도 = 다음 노드가 방문했는지 시간 + 각 노드 방문 시간
- DFS가 BFS에 비해 구현은 쉽지만 검색 속도는 느림

# 5. 동적 프로그래밍

# 6. 그리디 알고리즘
## (1) 그리디 알고리즘 수행과정
- 1단계 : 해 선택
  - 현재 상태에서 가장 최선이라고 생각되는 해를 선택
- 2단계 : 적절성 검사
  - 현재 선택한 해가 전체 문제의 제약 조건에 벗어나지 않는지 검사
- 3단계 : 해 검사
  - 현재까지 선택한 해 집합이 전체 문제를 해결할 수 있는지 검사
  - 전체 문제를 해결하지 못한다면 1단계로 돌아가 과정 반복
## (2) 대표 예시
- 회의실 예약

# 7. 심화 알고리즘
## (1) 이진 탐색 (Binary Search) : O(logN)
- **데이터가 정렬되어 있는 상태**에서 원하는 값을 찾아내는 알고리즘
- 중앙값 비교를 통한 탐색 범위 절반씩 축소
- 탐색 과정
  - 현재 데이터셋의 중앙값(median) 선택
  - 중앙값 > 타깃 데이터 : 중앙값 기준으로 왼쪽 데이터셋 선택
  - 중앙값 < 타깃 데이터 : 중앙값 기준으로 오른쪽 데이터셋 선택
  - 반복하다가 중앙값 == 타깃 데이터일 때 탐색 종료
- 문제 : doit_29 ~ doit_31