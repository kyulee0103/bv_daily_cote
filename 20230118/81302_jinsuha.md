# 풀이 
20분
# 코드
```python
#BFS를 사용해 탐색
from collections import deque

def bfs(p):
    start = []
    
    for i in range(5): 
        for j in range(5):
            if p[i][j] == 'P':
                start.append([i, j])
    
    for s in start:
        queue = deque([s])
        visited = [[0]*5 for i in range(5)]
        distance = [[0]*5 for i in range(5)]
        visited[s[0]][s[1]] = 1
        
        while queue:
            y, x = queue.popleft()
        
            dx = [-1, 1, 0, 0]  # 좌우
            dy = [0, 0, -1, 1]  # 상하

            for i in range(4):
                nx = x + dx[i]
                ny = y + dy[i]

                if 0<=nx<5 and 0<=ny<5 and visited[ny][nx] == 0:
                    
                    if p[ny][nx] == 'O':
                        queue.append([ny, nx])
                        visited[ny][nx] = 1
                        distance[ny][nx] = distance[y][x] + 1
                    
                    if p[ny][nx] == 'P' and distance[y][x] <= 1:
                        return 0
    return 1


def solution(places):
    answer = []
    
    for p in places:
        answer.append(bfs(p))
    
    return answer
```
# 풀이 방법
처음에 전체 탐색을 통해 풀었는데, 더 최적화된 알고리즘으로 거리가 2인 BFS를 사용해 탐색했습니다. 그때 X를 만나면 더이상 탐색하지 않습니다.

# 리뷰
map에서 거리를 찾는 일은 BFS 알고리즘을 적극적으로 활용해야 겠습니다.
