# 풀이
20분
#코드
```python
def solution(n, k, enemy):
    answer = 0
    for m in range(1,len(enemy)+1):
        if(small(n,k,m,enemy)):
            answer = answer + 1
        else:
            break
    return answer

def small(n,k,m,enemy):
    sum = 0
    if(m <= k):
        return 1
    else:  
        enemy_c = enemy[:m]
        enemy_c.sort(reverse=True)
        i = k
        while(i < m):
            sum += enemy_c[i]
            i = i + 1
        if(sum <= n):
            return 1
        else:
            return 0
  ```
  # 풀이 시간 
  1. 작은 문제로 바꿔서 풀생각을 해서 recursive function을 이용했습니다.
  2. 먼저 내림차순한 리스트에서 앞에서 k개만큼 제외하고 (m-k)개를 더함.
  3. 이 값이 n을 넘으면 1을 반환해서 answer값을 증가
  # 리뷰
  생각하기 어려울때 크기를 작게만들어서 생각하자!
