
# 코드
```python
def solution(lottos, win_nums):
    answer = []
    result = 0
    zero = 0
    for i in range(len(lottos)):
        if(lottos[i] in win_nums):
                   result += 1
        elif lottos[i] == 0:
                   zero += 1
    if result == 0 and zero == 0:
        answer.append(6)
        answer.append(6)
    elif result == 1 or result == 0:
        answer.append(7 - result - zero)
        answer.append(6)
    else:
        answer.append(7 - result - zero)
        answer.append(7 - result)

    return answer
```
# 풀이 방법
루프돌면서 해당 값이 배열에 있으면 result 증가, 0이 있으면 zero증가
# 리뷰
경계값 고려하자..
