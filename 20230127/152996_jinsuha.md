# 풀이 시간
실패..ㅋㅋㅋ
# 코드
```python
def solution(weights):
    answer = 0
    rate = [1,2,3,4,3/2,4/3]
    w = [0] * 901
    for i in range(len(weights)):
        w[weights[i] - 100] += 1
    print(w)
    for i in range(901):
        for r in rate:
            if(w[i]):
                rw= float(r*(i+100))
                if(rw <= 1000 and rw.is_integer()):
                    rw = int(rw)
                    if(w[rw-100]):
                        answer += 1
                
    return answer
```
# 풀이 방법
1. 몸무게를 담는 901칸의 배열을 만들고
2. 이에 rate를 곱해서 겹치는 값들을 쭉 찾도록해서 시간 초과문제를 해결하려 했습니다.
# 리뷰
두번 세어진 경우가 있어서 이를 수정해야합니다. 주말에 할 예정
100 , 100의 경우 200,200,300,300,400,400이 있는데 이것이 각자 다른 것으로 코드를 작성해 실패한거 같습니다.
