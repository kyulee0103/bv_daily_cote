# 풀이
15분
# 코드
```python
def solution(k, tangerine):
    answer = 0
    size = [0]*99999
    for t in tangerine:
        size[t-1] += 1
    size.sort(reverse=True)
    for s in size:
        k = k - s
        if(k > 0):
            answer += 1
            continue
        elif(k <= 0):
            answer += 1
            break
    return answer
```
# 풀이방법
1. 귤 크기에 따라 개수를 기록한 list 선언
2. 배열을 돌면서 해당 크기의 값을 +=1
3. 내림 차순으로 sort하면, size list를 돌때 큰순으로 빼면 된다.
