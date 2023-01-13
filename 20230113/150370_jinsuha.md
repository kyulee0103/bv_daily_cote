# 코드
```python
import re

def solution(today, terms, privacies):
    answer = []
    term_dic ={}
    final_day=[]
    privacy_=[]
    for term in terms:
        term.split(' ')
        term_dic[term[0]] = int(term[2:])
    print(term_dic)
    for privacy in privacies:
        privacy_.clear()
        privacy_= re.split('[.| ]',privacy)
        print(privacy_[0])
        print(int(privacy_[1]) + term_dic[privacy_[3]] )
        print(privacy_[2])
        final_day.append(int(privacy_[0])*28*12+ (int(privacy_[1]) + int(term_dic[privacy_[3]]))*28 + int(privacy_[2]))
    today_=today.split('.')
    today_by_day = int(today_[0])*28*12 + int(today_[1]) * 28 + int(today_[2])
    print(today_by_day)
    i = 1
    for final in final_day:
        print(final)
        if(today_by_day >= final):
            answer.append(i)
        i = i + 1
        
    return answer
```
# 풀이 방법
1. 전부 일로 바꾸어서 계산
# 리뷰
달을 28일로 보니까 년은 28*12인거를 생각못해서 오래걸렸다..
