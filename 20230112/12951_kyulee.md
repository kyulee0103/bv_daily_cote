## 풀이 시간
10분

## 소스코드
```jsx
function solution(s) {
    const lowerS = s.toLowerCase()
    const arr = lowerS.split(' ')
    for (let i = 0; i < arr.length; i += 1) {
        if (arr[i].length != 0) {
            if (arr[i][0].match(new RegExp(/^[a-z]/)) !== null) {
                let boxArr = arr[i].split('')
                boxArr[0] = boxArr[0].toUpperCase()
                arr[i] = boxArr.join('')
            }
        }
    }
    return arr.join(' ')
}
```

## 풀이 과정
맨 처음에 전체 string을 모두 lowercase로 바꿔줌.   
string은 바로 특정 위치 수정이 안돼서 array 형태로 바꿔서 수정 후에 다시 string으로 바꿔줌. (소문자로 시작하는 단어에 대해서만 변환)
