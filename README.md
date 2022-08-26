# [BOJ_피보나치 수_2920](https://www.acmicpc.net/problem/2747)
***
### My_code
```python
n = int(input())

arr = [0]*(n+1)
arr[1] = 1

for i in range(2, n+1):
    arr[i] = arr[i-2]+arr[i-1]

print(arr[n])
```
|출저|유형|자료형|
|:---:|:---:|:---:|
||DP|list|
* index out of range 주의.
