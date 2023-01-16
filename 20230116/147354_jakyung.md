## 풀이 시간
20분

## 소스코드
```python
def solution(data, col, row_begin, row_end):
    answer = 0
    s_i = []
    _sum = 0
    data = sorted(data,key = lambda x : (x[col-1],-x[0]))
    for r in range(row_begin-1,row_end):
        _sum = 0
        for e in data[r]:
            _sum += e % (r+1)
        s_i.append(_sum)
    #answer = bitwise_XOR(s_i)
    for i in s_i:
        answer = answer ^ i
    return answer
    
def bitwise_XOR(numbers):
    result = 0
    counter = 1
    rem = len(numbers)
    while rem > 0:
        ones = 0
        tmp = []
        for n in range(len(numbers)): # 각 bit 별 XOR
            if numbers[n]%2 == 1:
                ones += 1
            numbers[n] //= 2
            if numbers[n] != 0:
                tmp.append(numbers[n])
            else:
                rem -= 1
        numbers = tmp

        if ones % 2 == 1:
            result += counter
        counter *= 2

    return result
        
```

## 풀이 과정
# col 번째 열 기준 정렬[오름차순] (if 같으면)-> 1 번째 열 기준 정렬 (기본 키)[내림차순]

# S_i = i 번째 (tuple) 의 각 요소 % i 의 합

# 000 100 = 100

직접 bitwise_XOR 까지 구현을 하여 시간이 오래 걸렸음.
implementation 문제로 보이며, 문제 조건을 빠르게 파악하는게 핵심.