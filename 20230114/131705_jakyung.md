## 풀이 시간
1분

## 소스코드
```python
def solution(number):
    answer = 0
    for  i in range(len(number)-2):
        for j in range(i+1,len(number)-1):
            for k in range(j+1,len(number)):
                if number[i]+number[j]+number[k] == 0:
                    answer += 1
    return answer

```

## 풀이 과정
이번 문제는 기본적으로 n이 max 13이기 때문에 O(n^3)의 알고리즘을 사용하더라도 크게 느리지 않을 것임.
그냥 pair of 3를 만들면 될듯!