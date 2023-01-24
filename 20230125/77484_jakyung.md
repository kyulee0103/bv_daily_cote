## 풀이 시간
3분

## 소스코드
```python
def solution(lottos, win_nums):
    answer = [0,7]
    lotto_set = set(win_nums)
    for i in range(6):
        if lottos[i] in lotto_set:
            answer[1] -= 1
        elif lottos[i] == 0:
            answer[0] += 1
    answer[0] = answer[1] - answer[0]
    if answer[1] == 7:
        answer[1] -= 1
    if answer[0] == 7:
        answer[0] -= 1
    return answer
```

## 풀이 과정
set를 사용하고 For 문을 최소화하여 효율성을 올리고자 했으나 오히려 반례가 발생하여
비효율적이고 잡스러운 코드가 되었다.
0개 맞춘 것과 1개 맞춘 것이 둘다 6등이 되도록 하는 것이 문제였는데,
모범 답안을 보니
ranks = [6,6,5,4,3,2,1] 와 같은 배열을 생성하여 ranks의 index를 
이용하는 것이 좋다는 것을 알게 되었다.
'''python
def solution(lottos, win_nums):
    ranks = [6,6,5,4,3,2,1]
    lotto_set = set(win_nums)
    matches = 0
    for i in lottos:
        if i in lotto_set:
            matches += 1
    return [ranks[lottos.count(0)+matches],ranks[matches]]
'''
하면 제일 빠름!

오늘의 핵심: Index를 이용하면 더 효율적이므로 정답을 위한 배열을 하나 만들자!
