# 풀이
```python
def solution(cap, n, deliveries, pickups):
    give = [delivery for delivery in deliveries]
    take = [pickup for pickup in pickups]
    
    for i in range(n-2, -1, -1):
        give[i] = give[i+1] + give[i]
        take[i] = take[i+1] + take[i]
    
    sumCap = 0
    answer = 0
    for i in range(n-1, -1, -1):
        target = max(give[i], take[i])
        if target == 0: break
        if target > sumCap:
            visitFrequency = (target - sumCap) // cap + (1 if target % cap else 0)
            answer += (i+1) * visitFrequency
            sumCap += visitFrequency * cap
    
    return answer * 2
```
# 풀이방법
1. 배달과 수거는 사실 상관없음
2. 배달 배열과 수거 배열을 뒤에서부터 잡아먹으면서 target
