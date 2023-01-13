## 풀이 시간

30분

## 소스 코드

```python
def date_to_int(date_str):
    date_lst = date_str.split('.')
    return [int(date_lst[0]),int(date_lst[1]), int(date_lst[2])]

def add_date(date, add_month):
    date_lst = date_to_int(date)
    year = date_lst[0]
    added_month = date_lst[1] + add_month
    while added_month > 12:
        year += 1
        added_month -= 12
    return [year, added_month, date_lst[2]]

def is_expire(today, expday):
    for i in range(3):
        if today[i] < expday[i]:
            return False
        if today[i] > expday[i]:
            return True
    return True

def solution(today, terms, privacies):
    answer = []
    terms_lst = []
    today_date_lst = [int(t_str) for t_str in today.split('.')]

    for t in terms:
        terms_lst.append(t.split(' '))

    for idx, p in enumerate(privacies):
        for term in terms_lst:
            if p[-1] == term[0]:
                month = int(term[1])
                break
        limit_date_lst = add_date(p[:10], month)
        if is_expire(today_date_lst, limit_date_lst):
            answer.append(idx+1)

    return answer
```

## 풀이 과정

1. terms 내의 string으로 된 원소들을 list에 저장
2. 저장한 terms_lst를 기반으로 추가되는 달을 더해서 그 날을 오늘날짜와 비교
   뭔가 더 좋은 방법이 있을거 같은데 댕청댕청,, 머리가 나쁘면 손이 고생
