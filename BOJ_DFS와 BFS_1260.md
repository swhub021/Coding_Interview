# [BOJ_DFS와 BFS_1260](https://www.acmicpc.net/problem/1260)
***
### Lecture_code
```python
from collections import deque

def dfs(v):                 # 재귀로 구현.
    print(v, end=' ')       # 현재 정점 출력 후 
    visited[v] = True       # 방문 처리.
    for e in adj[v]:        # 현재 정점(v)에 연결되어 있는 아직 방문하지 않은 모든 정점들(e)에 대해서 | adj[v]: v의 인접 정점들을 담고있는 list.
        if not(visited[e]):
            dfs(e)          # DFS를 재귀적으로 수행.

def bfs(v):                         # 17~20): 탐색을 시작하는 현재 정점을 처리하는 과정.
    q = deque([v])                  # 21~23): 현재 정점에서 인접한 정점들 중 방문하지 않은 정점들, 즉 다음 정점들은 Queue에 넣는 과정.
    while q:                        # Queue가 빌 때까지 반복적으로 수행
        v = q.popleft()
        if not(visited[v]):
            visited[v] = True
            print(v, end=' ')
            for e in adj[v]:        # adj[v]: 현재 정점(v)에 인접한 정점들이 담긴 리스트.
                if not visited[e]:  # 현재 정점(v)에 연결되어 있는 아직 방문하지 않은 모든 정점들(e)을
                    q.append(e)     # Queue에 append함으로써 BFS 수행.

n, m, v = map(int, input().split())
adj = [[] for _ in range(n + 1)]        # 연결리스트를 이용하여 인접리스트를 담는다. 정점은 1~N이므로 list의 크기는 n+1로 설정.
for _ in range(m):                      # 간선의 개수(m)만큼 수행.
    x, y = map(int, input().split())    # 두 정점 x, y.
    adj[x].append(y)                    # 두 정점이 연결되어 있다면 각자의 연결리스트에 상대방을 append.
    adj[y].append(x)

                # '방문할 수 있는 정점이 여러 개인 경우에는 정점 번호가 작은 것을 먼저 방문'
for e in adj:   # adj: 모든 정점들에 대한 연결리스트. | e: adj의 일부로서, 각각의 정점들에 대한 연결리스트.
    e.sort()    # 각각의 정점들에 대한 연결리스트들을 오름차순 정렬함으로써 DFS/BFS 수행시 가장 낮은 번호부터 방문하도록 함.

visited = [False] * (n + 1) # 한 번 방문한 정점은 다시 방문하지 않도록 기록하는 역할. False: 방문 X, True: 방문 O.
dfs(v)
print()
visited = [False] * (n + 1)
bfs(v)
```
|출저|유형|자료형|시간복잡도|
|:---:|:---:|:---:|:---:|
|3_ch02_11|DFS, BFS|list|O(N+M)|
* 연결리스트(adj): 각각의 모든 정점들에 대해, 연결되어 있는 각각의 정점들에 대한 정보를 담고 있음.
* DFS 구현: 1) 재귀 2) 스택

* 초기 과정:<br/> 1) 빈 리스트를 한 단위로 한 연결리스트(adj) 생성.<br/> 2) 각 정점들에 대한 연결리스트 생성.<br/>3) 정점 번호가 작은순으로 방문하기 위한 오름차순 정렬.<br/> 4) 방문 여부를 기록하기 위한 list 생성후, 탐색 시작 정점(v)을 매개변수로 하는 함수 호출.  
* DFS(v):<br/>  1) 현재 정점(v)을 출력 후, 방문 처리.<br/> 2) v의 인접 정점들 중 아직 방문하지 않은 정점에 대해 다시 DFS 수행.
* BFS(v):<br/>  1) 현재 정점(v)을 담고 있는 Queue 생성.<br/> 2) 시간순으로 가장 먼저 Queue에 삽입된 정점을 꺼낸다.<br/>3) 아직 방문하지 않은 정점이라면 방문 처리 후, 출력.<br/>4) 현재 정점과 인접한 정점들 중 아직 방문하지 정점들을 Queue에 삽입.<br/>5) 2)~5) 과정을 Queue가 empty가 될 때까지 반복.


