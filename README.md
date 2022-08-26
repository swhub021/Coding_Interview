# [BOJ_좌표 정렬하기_11650](https://www.acmicpc.net/problem/11650)
***
### My_code
```python
N = int(input())
arr = []

for _ in range(N):
    x, y = input().split()
    arr.append((int(x), int(y)))
arr = sorted(arr)

for tmp in arr:
    print(tmp[0], tmp[1])
```

|출저|유형|자료형|
|:---:|:---:|:---:|
|3_ch02_02|정렬|list|

* sorted(): key 속성 설정 없이 sorted()를 이용할 경우, x좌표, y좌표 (인덱스)순으로 차례대로 오름차순 정렬.
