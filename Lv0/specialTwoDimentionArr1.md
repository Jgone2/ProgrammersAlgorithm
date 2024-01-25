# 특별한 이차원 배열 1

## 📌 문제 설명

정수 n이 매개변수로 주어질 때, 다음과 같은 n × n 크기의 이차원 배열 arr를 return 하는 solution 함수를 작성해 주세요.

- arr[i][j] (0 ≤ i, j < n)의 값은 i = j라면 1, 아니라면 0입니다.

### 제한 조건

- 1 ≤ n ≤ 100

### 입출력 예

| n | result |
| - | ------ |
| 3 | \[[1, 0, 0], [0, 1, 0], [0, 0, 1]\] |
| 6 | \[[1, 0, 0, 0, 0, 0], [0, 1, 0, 0, 0, 0], [0, 0, 1, 0, 0, 0], [0, 0, 0, 1, 0, 0], [0, 0, 0, 0, 1, 0], [0, 0, 0, 0, 0, 1]] |
| 1 | \[[1]] |

# 🧐 접근

이중for문 사용

```java
class Solution {
    public int[][] solution(int n) {
        int[][] answer = new int[n][n];
        for (int i = 0; i < answer.length; i++) {
            for (int j = 0; j < answer.length; j++) {
                if (i == j) answer[i][j] = 1;
                else answer[i][j] = 0;
            }
        }
        return answer;
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### ===============