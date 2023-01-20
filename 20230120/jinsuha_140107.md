# 풀이 시간
20분
# 코드
```python
def solution(k, d):
    answer = 0
    for x in range(0,d+1,k):
            answer += (int((d**2 - x**2)**(1/2)))//k + 1

    return answer
```
# 풀이방법
격자점 수 세기를 한루프를 끝냈습니다.
# 리뷰
처음에 x와 y를 2개로 해서 루프 돌렸더니 시간초과가 나와서 최대한 한 루프안에 끝내도록 수정했습니다.
