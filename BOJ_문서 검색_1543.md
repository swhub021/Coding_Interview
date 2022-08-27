# [BOJ_문서 검색_1543](https://www.acmicpc.net/problem/1543)
***
### Lecture_code
```python
document = input()
word = input()
idx = 0
cnt = 0

while len(document)-idx >= len(word):
    if document[idx:idx+len(word)] == word:
        cnt += 1
        idx += len(word)
    elif document[idx:idx+len(word)] != word:
        idx += 1

print(cnt)
```
|출저|유형|자료형|
|:---:|:---:|:---:|
|3_ch02_05|탐색|list|
* 아이디어: 현재 인덱스에서 문서와 단어가 중복될 경우 카운팅 후 단어의 크기만큼 이동 후 중복 여부 판별,<br/>
중복되지 않는 경우 바로 다음 인덱스로 이동 후 중복 여부 판별.
* 문서의 길이는 최대 2500, 단어의 길이는 최대 50으로 O(NM) = O(2500*50)이므로 모든 경우를 탐색해서 답을 찾는 것이 가능.

