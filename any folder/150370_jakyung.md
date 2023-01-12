## 풀이 시간
25분

## 소스 코드
```python
def solution(today, terms, privacies):
    answer = []

    terms_dict = {}
    for t in terms: #save terms as dictionary
        a,b = t.split()
        terms_dict[a] = int(b)
    
    td = list(map(int,today.split('.')))
    td[2] += 1
    for i in range(len(privacies)):
        date, term = privacies[i].split()
        date = list(map(int,date.split('.')))
        tmp = date[1]
        date[1] = (date[1] + terms_dict[term]-1) % 12 + 1 ## 여기서 처음에 틀림
        date[0] += terms_dict[term] // 12
        if tmp > date[1]: date[0] += 1

        for j in range(3):
            if date[j] < td[j]:
                answer.append(i+1)
                break
            elif date[j] > td[j]:
                break
    return answer
```

```jsx
function solution(today, terms, privacies) {
    let answer = [];

    let terms_dict = {};
    for (let t of terms) { //save terms as dictionary
        let [a,b] = t.split(" ");
        terms_dict[a] = parseInt(b);
    }
    
    let td = today.split(".").map(x => parseInt(x));
    td[2] += 1;
    for (let i = 0; i < privacies.length; i++) {
        let [date, term] = privacies[i].split(" ");
        date = date.split(".").map(x => parseInt(x));
        let tmp = date[1];
        date[1] = (date[1] + terms_dict[term] - 1) % 12 + 1;
        date[0] += Math.floor(terms_dict[term] / 12);
        if (tmp > date[1]) { 
            date[0] += 1;
        }

        for (let j = 0; j < 3; j++) {
            if (date[j] < td[j]) {
                answer.push(i+1);
                break;
            } else if (date[j] > td[j]) {
                break;
            }
        }
    }
    return answer;
}
```

## 풀이 과정
1. terms 내의 string으로 된 원소들을 parsing하여 dictionary/object에 저장을 한다.
2. privacies의 원소들(날짜)는 '.'을 기준으로 parsing하여 날짜와 terms로 나눈다.
3. for loop으로 iterate하여 개인정보 수집 일자에 유효기간을 더하여 유효 날짜를 구한다.
4. today와 유효날짜를 비교하여 today가 유효 기간을 넘었을 경우에는 파기할 개인정보(result)로 추가한다.
