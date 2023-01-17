## 풀이 시간
깜빡하고 시간을 안쟀는데 대충 삼사십분?

## 소스 코드
```javascript
function solution(id_list, report, k) {
    let reportArr = report.map((x) => x.split(' '))
    let reporting = {}
    let reported = {}
    for (let id of id_list) {
        let reportingSet = new Set()
        let reportedSet = new Set()
        reporting[id] = reportingSet
        reported[id] = reportedSet
    }
    for (let i = 0; i < reportArr.length; i += 1) {
        reporting[reportArr[i][0]].add(reportArr[i][1])
        reported[reportArr[i][1]].add(reportArr[i][0])
    }
    let stop = []
    for (let name of Object.keys(reported)) {
        reported[name].size >= k ? stop.push(name) : null
    }
    let answer = []
    for (let name of Object.keys(reporting)) {
        let cnt = 0
        for (let mail of stop) {
            if (reporting[name].has(mail)) {
                cnt += 1
            }
        }
        answer.push(cnt)
    }
    return answer
}
```

## 풀이 과정
처음에는 includes를 사용해서 조건문 처리 했는데 시간초과가 떠서 Set으로 바꿔서 다시 풀어씀
