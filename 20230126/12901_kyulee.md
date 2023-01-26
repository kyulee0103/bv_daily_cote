## 소요 시간
10분

## 소스 코드
```javascript
function checkDay(date) {
    if (date % 7 === 0) {
        return 'THU'
    } else if (date % 7 === 1) {
        return 'FRI'
    } else if (date % 7 === 2) {
        return 'SAT'
    } else if (date % 7 === 3) {
        return 'SUN'
    } else if (date % 7 === 4) {
        return 'MON'
    } else if (date % 7 === 5) {
        return 'TUE'
    } else if (date % 7 === 6) {
        return 'WED'
    }
}

function solution(a, b) {
    const days = [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    let plusDays = 0
    for (let i = 0; i < a - 1; i += 1) {
        plusDays += days[i]
    }
    return checkDay(plusDays + b)
}
```

## 풀이 과정
`%7` 값 이용
