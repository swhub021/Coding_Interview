# [BOJ_바이러스_2606](https://www.acmicpc.net/problem/2606)
***
### My_code
```python
def DFS(v):
    global count
    visited[v] = 1
    count += 1
    for e in adj[v]:
        if visited[e] == 0:
            DFS(e)
    return count

node = int(input())
link = int(input())

adj = [[] for _ in range(node+1)]

count = -1   # "1번 컴퓨터를 통해 웜 바이러스에 걸리게 되는 컴퓨터의 수를 출력" 
             # 시작 정점은 카운팅에서 제외해야하므로 count -1. 

for _ in range(link):
    x, y = map(int, input().split())
    adj[x].append(y)
    adj[y].append(x)

visited = [0]*(node+1)
print(DFS(1))
```

***
### Lecture_code
```python
n = int(input())
m = int(input())

adj = [[] for _ in range(n + 1)]
visited = [False] * (n + 1)
count = 0

for _ in range(m):
    x, y = map(int, input().split())
    adj[x].append(y)
    adj[y].append(x)

def dfs(now_pos):
    global count
    count += 1
    visited[now_pos] = True
    for next_pos in adj[now_pos]:
        if not visited[next_pos]:
            dfs(next_pos)

dfs(1)
print(count - 1)
```
|출저|유형|자료형|시간복잡도|
|:---:|:---:|:---:|:---:|
|3_ch02_12|DFS/BFS|list|@|

```python
* DFS, BFS로 모두 풀이 가능.
* 컴퓨터의 수가 100이하로 적으므로, 상대적으로 BFS보다 코드의 길이는 짧으나 속도는 느린 DFS로도 풀이 가능.
```
