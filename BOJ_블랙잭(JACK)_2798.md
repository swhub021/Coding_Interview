# [BOJ_블랙잭(JACK)_2798](https://www.acmicpc.net/problem/2798)
***
### My_code
```python
N, M = map(int, input().split())
arr = list(map(int, input().split()))
res = -2147000000
for i in range(N):
    for j in range(i+1, N):
        for k in range(j+1, N):
            tmp = arr[i]+arr[j]+arr[k]
            if tmp<=M:
                if tmp>res:
                    res = tmp
print(res)
```
***
|출저|유형|자료형|
|:---:|:---:|:---:|
|3_ch01_01|완전탐색|list|
* Python은 초당 2천만 번 정도의 연산을 수행.
* 모든 경우의 수는 조합 C(N, 3). N이 최대(100)인 경우도 (100*99*98)/3!도 161700 밖에 안되므로 3중 for문으로 풀이 가능.
