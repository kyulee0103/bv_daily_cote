## 풀이 시간
30분

## 소스코드
```python
def solution(people, limit):
    answer = 0
    weight = [0]*241
    for i in people:
        weight[i] += 1
    _min = 40
    _max = 240
    
    for i in range(40,241): #min weight 구하기 (O(k))
        if weight[i] != 0:
            _min = i
            break
            
    for i in range(240,39,-1): #max weight 구하기 (O(k))
        if weight[i] != 0:
            _max = i
            break
    while(1): #O(k)
        while(weight[_min]==0):
            _min += 1
        while(weight[_max]==0):
            _max -= 1
        if _min < _max:
            if _min + _max <= limit:
                if weight[_min] > weight[_max]:
                    answer += weight[_max]
                    weight[_min] -= weight[_max]
                    _max -= 1
                elif weight[_min] < weight[_max]:
                    answer += weight[_min]
                    weight[_max] -= weight[_min]
                    _min += 1
                else:
                    answer += weight[_min]
                    _min += 1
                    _max -= 1
            else:
                answer += weight[_max]
                _max -= 1
        else:
            break
    if(_min == _max):
        if _min + _max <= limit:
            answer += (weight[_min] + 1) // 2
        else:
            answer += weight[_min]
                
    return answer

```

## 풀이 과정
처음에 문제를 읽을 때 보트 최대 인원 2 라는 조건을 못봐서 상당한 삽질을 하여 시간을 많이 씀.
보통 푸는 방식은 투 포인터를 사용하여 iterate하면서 비교를 통해 보트의 수를 구하는 것이 
일반적이지만, 선제 조건은 sort를 사용하는 것인데, 이는 O(nlogn)의 시간이 소요된다.

나의 알고리즘은 정렬을 사용하지 않고 weight에 따라 사람의 수를 저장하여 O(k) 상수 시간에
이를 마치고, O(k)의 상수 시간에 비교를 통해 직접적인 사람에 대한 투포인터를 사용하는 것이
아닌, weight에 관해서 투포인터를 사용하여 시간을 절약하였음.
실제로 효율성면에서 일반적인 방법에 비해 3~4배 더 빨랐음.