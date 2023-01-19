# 풀이 시간
10분
# 코드
```python
def solution(n, arr1, arr2):
    answer = []
    result = []
    #bitwise or
    for i in range(n):
        o = arr1[i] | arr2[i]
        print(o)
        a = ""
        for j in range(n):
                if(o%2 == 1):
                    a = "#" + a
                    o = o//2
                else:
                    a = " " + a
                    o = o//2
            
        answer.append(a)
    return answer
```
# 풀이 방법
1. bitwise or를 통해 벽의 여부를 계산
2. 이진수 변환과 동시에 #을 추가할지 안할지 결정 
