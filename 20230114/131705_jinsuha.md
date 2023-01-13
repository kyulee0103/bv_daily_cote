# 풀이 시간
5분
# 코드 
```python
from itertools import combinations
def solution(number):
    answer = 0
    
    combination = list(combinations(number,3))
    for comb in combination:
        if(sum(comb) == 0):
            answer = answer + 1
    
    return answer
 ```
 # 풀이 방법
 1. 조합을 사용해 가능한 튜플을 뽑고
 2. 이를 합한 0일때 answer + 1
