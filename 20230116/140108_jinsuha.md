# 풀이 시간
15분

# 코드
```python
def solution(data, col, row_begin, row_end):
    answer = 0
    data = sorted(data,key = lambda x:[x[col-1],-x[0]])
    
    for i in range(row_begin,row_end+1):
        sum = 0
        for d in data[i-1]:
            sum += (d % i) 
        answer ^= sum
    
    return answer
```
# 풀이 방법
2차원 배열 sorted로 col-1값기준으로 오름차순 그리고 첫 값을 기준으로 내림차순
그리고 sorted된 2차원 배열을 접근해 나머지를 계산해서 answer와 bitwise xor 계산
# 리뷰
python의 sort와 sorted함수를 잘
