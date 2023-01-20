# 풀이 시간
10분
# 코드 
```python
def solution(s):
    answer = []
    character=[-1]*26# 소문자의 위치
    for i in range(len(s)):
        if(character[ord(s[i])-ord('a')] == -1):
            answer.append(-1)
            character[ord(s[i])-ord('a')] = i
        else:
            answer.append( i - character[ord(s[i])-ord('a')]) # 지금 위치 - 그전 위치
            character[ord(s[i])-ord('a')] = i
        
    return answer
```
# 풀이 방법
1. 최근 탐색한 문자의 위치를 담는 배열을 -1로 초기화
2. 문자열을 돌다가 character 배열에 있는 값이 -1인경우(처음 발견한 문자라는 뜻)이면 그 문자의 위치를 저장하고 -1을 answer에 추가
3. 그렇지 않은 경우에 character에 그 문자의 위치를 저장하고 그리고 i - character[ord(s[i])-ord('a')](지금 위치 - 그전 위치)를 answer에 추가합니다.
