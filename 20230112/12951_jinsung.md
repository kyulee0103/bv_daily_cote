## 풀이 시간

40분

## 소스 코드

```py
def solution(s):
    answer = ''
    char_uc_lst = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    char_lc_lst = "abcdefghijklmnopqrstuvwxyz"
    num_lst = "0123456789"
    flag = True

    for i in range(len(s)):
        if s[i] == ' ':
            answer += " "
            flag = True
            continue
        try:
            answer = answer + str(int(s[i]))
            flag = False
        except:
            is_upper = s[i] in char_uc_lst
            if flag == is_upper:
                answer += s[i]
                flag = False
            else:
                if is_upper:
                    for idx, c in enumerate(char_uc_lst):
                        if c == s[i]:
                            answer += char_lc_lst[idx]
                            flag = False
                            break
                elif not is_upper:
                    for idx, c in enumerate(char_lc_lst):
                        if c == s[i]:
                            answer += char_uc_lst[idx]
                            flag = False
                            break
    return answer
```

## 풀이 과정

1. int()로 숫자를 걸러주고 문자열에 대한 처리만 함
2. 공백의 여부를 flag로 판단했음
3. 공백의 유무와 대문자인지 소문자인지에 따라 경우를 나누어 대문자->소문자, 소문자->대문자 로 바꿈

- 최대한 내장함수를 안써보려 했음, 내장함수를 써서 모두 바꾸는 것보다는 바꿀 필요성이 있을때만을 판단하여 최대한 효율적으로 짜보려 했음, 또 그냥 평범한거 말고 재밌게 짜보고 싶어서 오류 발생시켜서 풀어 보았음. 좋은 코드인지는 모르겠으나 재밌음. 파이썬 오랜만이라 찾으면서 하다보니 오래걸림..
