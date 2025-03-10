# BOJ 16937번 [직사각형 탈출](https://www.acmicpc.net/problem/16973)

## 🌈 풀이 후기
* 시간초과가 많이 나서 힘들었습니다.
* 직사각형을 2중포문으로 매번 검사하니까 시간초과났습니다.  
그래서 벽인곳 왼쪽 위를 2로 초기화하고 isValid함수에서 한번에 직사각형을 검사했습니다.
## 👩‍🏫 문제 풀이
### 변수
* N: 격자판 세로크기
* M: 격자판 가로크기
* answer: 답
* H: 직사각형 세로크기
* W: 직사각형 가로크기
* (sr, sc) : 직사각형 시작좌표
* (fr, fc) : 직사각형 도착좌표
### 순서
* `map[y][x]=1` 인 곳을 arrayList에 저장합니다.
* `init()` arrayList 를 순회하면서 직사각형의 왼쪽 위 좌표가 갈 수 없는 곳을 2로 만듭니다. 
* bfs방법으로 직사각형이 도착좌표에 도착할 때까지 이동합니다.
* `y == fr && x == fc` 일 때 bfs를 종료합니다.
