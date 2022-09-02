# [BOJ_DFS와 BFS_1260](https://www.acmicpc.net/problem/1260)
***
### Lecture_code
```python
from collections import deque

def dfs(v):
    print(v, end=' ')
    visited[v] = True
    for e in adj[v]:
        if not(visited[e]):
            dfs(e)

def bfs(v):
    q = deque([v])
    while q:
        v = q.popleft()
        if not(visited[v]):
            visited[v] = True
            print(v, end=' ')
            for e in adj[v]:
                if not visited[e]:
                    q.append(e)

n, m, v = map(int, input().split())
adj = [[] for _ in range(n + 1)]
for _ in range(m):
    x, y = map(int, input().split())
    adj[x].append(y)
    adj[y].append(x)

for e in adj:
    e.sort()

visited = [False] * (n + 1)
dfs(v)
print()
visited = [False] * (n + 1)
bfs(v)
```
|출저|유형|자료형|시간복잡도|
|:---:|:---:|:---:|:---:|
|3_ch02_11|DFS, BFS|list|O(N+M)|
* 연결리스트를 이용.
```python

```
