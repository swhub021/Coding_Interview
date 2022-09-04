***
### My_code
```python
from collections import deque

s, e = map(int, input().split())

maximum = 10000
Line = [0]*(maximum+1)
visited = [0]*(maximum+1)
q = deque([s])

while True:
    now = q.popleft()
    
    if now == e:
        print(Line[now])
        break
    
    for NEXT in (now-1, now+1, now+5):
        if 1 <= NEXT <= maximum and visited[NEXT] == 0:
            visited[NEXT] = 1
            Line[NEXT] = Line[now] + 1
            q.append(NEXT)
```
|출저|유형|자료형|유사한 문제|
|:---:|:---:|:---:|:---:|
|7-7|BFS|deque, list|BOJ_숨바꼭질_1697|

