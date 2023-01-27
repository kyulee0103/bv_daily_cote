# 풀이 시간
3분
# 코드
```python
def solution(k, score):
    answer = []
    placek = []
    for s in score:
        placek.append(s)
        if(len(placek) > k):
            placek.pop(placek.index(min(placek)))
        answer.append(min(placek))       
    return answer
```
# 풀이 방법
k개가 되도록 list에 담아서 최소값을 계속해서 찾고 그 값을 pop하는 방식으로 쭉 진행한다.

# 리뷰
min heap을 사용하면 좀 더 빠르게 해결할 수 있을거 같습니다.
