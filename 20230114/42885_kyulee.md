## 풀이 시간
30분   

## 소스 코드
```jsx
function solution(people, limit) {
    let cnt = 0
    people.sort((a, b) => a - b)
    while (people.length != 0) {
        if (people[0] + people[people.length - 1] <= limit) {
            people.shift()
        }
        people.pop()
        cnt += 1
    }
    return cnt
}
```   

## 풀이 과정
아니 똑같은 코드인데 shift()랑 pop() 말고 people.splice(0,1)랑 people.splice(people.length-1,0)으로 할때는 통과 안되고 shift랑 pop 쓰니까 통과되네 ;;;    
쓸데없이 시간 날린 느낌...🥲
