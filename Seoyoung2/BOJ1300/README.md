# BOJ 1300번 [K번째 수](https://www.acmicpc.net/problem/1300)



## 🌈 풀이 후기

그냥 풀면 당연히 메모리초과나고,, 분류가 이분탐색이라 이분탐색을 써야겠는데 이분탐색을 어떤식으로 적용해야할지 모르겠던 문제이다.

이분탐색도 배열에 값을 넣은 후 정렬하고 탐색을 하는 방식으로 알고 있었는데 배열에 값을 넣는 것부터 다시 생각해야하는 어려운 문제였다. 

그래서 블로그 참조해서 문제를 해결했다. 이분탐색 문제라는 걸 모르고 풀면 절대 풀지 못할 문제같다,,ㅠㅠ

## 👩‍🏫 문제 풀이

우리가 구하려는 K번째 수를 S라고 했을 때, S는 1행부터 N행까지 i번째 행에서의 min(N, S/i) 을 더한 값이다.

1. 이분탐색을 위해 최소값인 left는 1(1행1열)로, 최댓값인 right는 K로 초기화한다. (K번째 수는 절대 K를 넘지 않는 수이기 때문에 N^2이 아닌 K로 초기화) 
2. 이분탐색 진행 <code>(left+right) / 2</code> 로 mid 값을 얻고 for문으로 행을 탐색하며 각 행에서 mid와 같거나 작은수를 카운트한다. => <code>cnt += Math.min(mid / i, N)</code> 
3. 위 수식에서 <code>mid/i</code>는 i번째 행의 원소들 중 mid 값보다 같거나 작은 원소의 개수
4. N값과 비교 후 최솟값을 구하는 이유는 한 행의 원소의 개수는 N개이기 때문에 mid/i의 값이 N보다 크게 나온다면 N을 카운트.
5. 모든 행을 돌며 카운트한 cnt 값과 K를 비교하여 이분탐색을 계속 진행한다.



** 블로그에서 풀이법을 이해하고 가져온 코드여서 다른 코드들과 별 차이 없을거에요,,