# [BOJ_음계(Note)_2920](https://www.acmicpc.net/problem/2920)
***
### My_code
```python
notes = input()

if notes == '1 2 3 4 5 6 7 8':
    print('ascending')
elif notes == '8 7 6 5 4 3 2 1':
    print('descending')
else:
    print('mixed')
```

***
### Lecture_code
```python
notes = list(map(int, input().split()))

ascending = True
descending = True

for i in range(1, 8):
    if notes[i] > notes[i-1]:
        descending = False
    elif notes[i] < notes[i-1]:
        ascending = False
        
if ascending:
    print('ascending')
elif descending:
    print('descending')
else:
    print('mixsed')

```
|출저|유형|자료형|
|:---:|:---:|:---:|
|3_ch01_01|구현|str/list|
* 아이디어: 리스트의 앞뒤 원소를 차례대로 비교하며 오름차순/내림차순 여부를 체크.
***
```python
# 입력값: 1 2 3
a = input.split()
print(a)
# 출력값: ['1', '2', '3']
```
```python
# 입력값: 1 2 3
a = map(int, input.split())
print(a)
# 출력값: <map object at 0x000001D6D90B5390>
```
```python
# 입력값: 1 2 3
a = list(map(int, input.split()))
print(a)
# 출력값: [1, 2, 3]
```
***
* Python3 vs PyPy3: PyPy3(메모리 사용 多 but 시간은 단축됨)
