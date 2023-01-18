# 풀이 시간
10분
# 코드
```python
def solution(s):
    answer = ""
    number = ""
    numbers=["zero","one","two","three","four","five","six","seven","eight","nine"]
    numbers_d = {"zero" : "0","one":"1","two":"2","three":"3","four":"4","five":"5","six":"6","seven":"7","eight":"8","nine":"9"}
    for c in s:
        if('0'<= c and c <='9'):
            answer = answer + c
            
        else:
                number = number + c
            
        if number in numbers:
                    answer = answer + numbers_d[number]
                    number = ""  
    result = int(answer)
            
    return result
```
# 풀이 방법
1. 숫자이면 바로 answer에 더하고
2. char이면 number에 더해서 numbers에 있는 숫자가 될때까지 누적한다.
3. 모든 for문이 끝나면 이르 int로 
