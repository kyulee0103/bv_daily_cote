## 풀이 시간

20분

## 소스 코드

```py
def solution(survey, choices):
    ct_dic = {'R':0, 'T':0, 'C':0, 'F':0,  'J':0, 'M':0, 'A':0, 'N':0 }
    answer = ''
    for idx, sc in enumerate(choices):
        if sc == 4:
            continue
        if sc < 4:
            ct = survey[idx][0]
            ct_dic[ct] += -sc + 4
        if sc > 4:
            ct = survey[idx][1]
            ct_dic[ct] += sc - 4

    if ct_dic['R'] >= ct_dic['T']:
        answer += 'R'
    else:
        answer += 'T'

    if ct_dic['C'] >= ct_dic['F']:
        answer += 'C'
    else:
        answer += 'F'

    if ct_dic['J'] >= ct_dic['M']:
        answer += 'J'
    else:
        answer += 'M'

    if ct_dic['A'] >= ct_dic['N']:
        answer += 'A'
    else:
        answer += 'N'

    return answer
```

## 풀이 과정

1. 성격 유향에 대한 딕셔너리 만듬
2. 점수가 4이면 빠른 패스
3. 4보다 작으면 앞의 문자가 관련있고 크면 뒤의 문자가 관련 있기 때문에 그걸 기반으로 if문 사용
4. 점수는 일정한 규칙이 있으니까 그 규칙성을 활용해서 딕셔너리 점수에 더해줌
5. 노가다로 문자 넣어주기

- 점수 더할떄 += 안쓰고 = 써서 5분 날림, 잘 보세~
