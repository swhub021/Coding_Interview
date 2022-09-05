# Inflearn_7-1
### My_code
```python
def dfs(v, score_sum, time_sum):
    global maximum_score

    if time_sum > M:
        return

    if v == N:
        if score_sum > maximum_score:
            maximum_score = score_sum
    else:
        for i in range(N):
            dfs(v+1, score_sum+S[i], time_sum+T[i])
            dfs(v+1, score_sum, time_sum)           # 점수 뿐만 아니라 시간 또한 해당 문제를 선택하지 않았으면 현재까지 시간의 총합에 추가되지 말아야 함. 


N, M = map(int, input().split())

S = []
T = []
for _ in range(N):
    score, solved_time = map(int, input().split())
    S.append(score)
    T.append(solved_time)

maximum_score = 0

dfs(0, 0, 0)

print(maximum_score)
```
***
|출저|유형|자료형|
|:---:|:---:|:---:|
|7-7|DFS(부분집합)|list|
* 함수명과 함수의 매개변수는 소문자로 작성할 것. 
