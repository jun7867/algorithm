# BOJ 1182번 [부분수열의 합](https://www.acmicpc.net/problem/1182)

## 🌈 풀이 후기
- 수업시간에 풀었던 햄버거 다이어트와 비슷한 방식으로 풀었습니다.
## 👩‍🏫 문제 풀이
### 아이디어
- 매 subset마다 포함된 각 값을 조회하여 더하는 방식이 번거롭다고 느꼈습니다.
- 그래서 더한 값을 미리 저장해두고, 새 값을 추가할때마다 이 값에 한번만 더하는 방식으로 작성하였습니다.
- ex) (편의상 2진수로 표기하겠습니다.)
    - sum[1000] = data + sum[0000];
    - sum[1001] = data + sum[0001];
    - sum[1010] = data + sum[0010];
    - ...
    - sum[1111] = data + sum[0111];
- 각 subset별 20번(N의 최대값)의 bitshift를 줄이는 대신, 2^N개의 공간복잡도를 얻었습니다;

### 풀이 방법
1. `int sum[]`배열을 1<<N 사이즈만큼 생성합니다.
2. N만큼 loop를 돌며
    2.1. 값을 1개 입력받습니다.
    2.2. 0 ~ (2 ^ N) - 1 만큼 Loop를 돌며
    2.3. N이 없었을때의 값에 N을 더하여 저장합니다.
    2.4. 이중 값이 S와 같은 경우를 카운트합니다.

