풀이 시간
10분

코드
def solution(s):
    answer = 1
    x = s[0]
    x_num = 0
    not_x_num = 0
    for i in range(len(s)):
        
        if(s[i] != x):
            not_x_num += 1
        else:
            x_num+= 1
            
        if(x_num == not_x_num and i != len(s) - 1):
            x = s[i+1]
            answer +=1
            x_num = 0
            not_x_num = 0
            
    return answer
풀이 방법
같을 때마다 분리~
