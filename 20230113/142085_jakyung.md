## 풀이 시간
20분

## 소스 코드
```python
import heapq
def solution(n, k, enemy):
    answer = 0
    rounds = []
    for i in range(len(enemy)):
        if n >= enemy[i]:
            n -= enemy[i]
            heapq.heappush(rounds,-enemy[i])
            answer += 1
        else:
            if k>0:
                k -= 1
                heapq.heappush(rounds,-enemy[i])
                n -= heapq.heappop(rounds)
                n -= enemy[i]
                answer += 1
            else:
                break

    return answer
```

## 풀이 과정
1. n 이 enemy[i] 보다 크거나 같을 경우에 n에서 enemy[i]만큼씩 빼주고 rounds에 enemy[i]를 저장해준다
2. 이때 rounds는 max heap처럼 동작하게 만들기 위해서 enemy[i] 대신 -enemy[i]를 삽입하였음
3. n 이 enemy[i] 보다 작을 경우에는 rounds에서 최댓값을 지닌 원소를 빼서 이를 '무적권' 하나와 교환을 한다. 이때 k -= 1 이 이루어진다.
4. '무적권' k가 한개도 남아 있지 않으며, enemy[i]가 n보다 크면 for loop을 멈추고, 이 때의 레벨이 최대 레벨이다.