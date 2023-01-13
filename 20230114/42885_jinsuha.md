# 풀이 시간 
20분
# 코드
```python
def solution(people, limit):
    people.sort()
    answer = 0
    right = len(people) - 1
    left = 0
    while right > left:
        if people[right] + people[left] <= limit: 
            right -= 1 
            left += 1
        else: 
            right -= 1 
        answer += 1
            
    if left == right: 
        answer += 1
    return answer
```
# 풀이 방법
1. 두포인터를 사용해 탐색
2. 먼저 sort를 하고 가장 큰값과 작은 값을 더해보고 limit보다 작으면 넘어가고 아니면 그 다음으로 큰값과 더해서 limit보다 작은지 확인. 이를 반복
3. 그러면 마지막에 left와 right가 같아지면 answer += 1 하고 종료
