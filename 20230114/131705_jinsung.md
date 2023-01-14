## 풀이시간

10분

## 코드

```python
def solution(number):
    answer = 0
    for i in range(len(number)):
        for j in range(i+1, len(number)):
            for k in range(j+1,len(number)):
                if number[i] + number[j] + number[k] == 0:
                    answer += 1
    return answer
```

## 풀이방법

MT여서 정답률 높은거 보고 그냥 골랐는데,, 너무 쉬운걸 골랐나..
