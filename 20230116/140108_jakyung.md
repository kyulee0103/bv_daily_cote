## 풀이 시간
10분

## 소스코드
```python
def solution(s):
    answer = 0
    cnt_x = 0
    cnt_nx = 0
    x = ''
    for i in s:
        if cnt_x == 0: #새로운 부분 문자열 시작
            x = i
            cnt_x = 1
        else: #이미 진행중인 부분 문자열
            if i == x:
                cnt_x += 1
            else:
                cnt_nx += 1
            if cnt_x == cnt_nx: # x의 개수 == non-x
                answer += 1
                cnt_x = cnt_nx = 0
    if cnt_x != cnt_nx:
        answer += 1
        
    return answer
```

## 풀이 과정
부분 문자열의 첫 문자를 저장하고 비교하며 cnt_x, cnt_nx에 저장하고
cnt_x == cnt_nx 가 되면 answer++ 을 한다.
