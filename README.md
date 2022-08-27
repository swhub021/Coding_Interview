# # [BOJ_K번째 수_11004](https://www.acmicpc.net/problem/11004)
***
### My_code
```python
N, K = map(int, input().split())
arr = list(map(int, input().split()))

arr.sort()

print(arr[K-1])
```
|출저|유형|자료형|
|:---:|:---:|:---:|
|3_ch02_04|정렬|list|
* 데이터의 수는 N(1 ≤ N ≤ 5,000,000) 많으나, 범위 또한 넓어서 (-10**9 ≤ Ai ≤ 10**9) 계수 정렬로는 풀 수 없음.
* PyPy3로 제출할 것.
