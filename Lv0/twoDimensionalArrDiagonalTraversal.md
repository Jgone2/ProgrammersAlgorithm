# 이차원 배열 대각선 순회하기

## 📌 문제 설명

2차원 정수 배열 board와 정수 k가 주어집니다.

i + j <= k를 만족하는 모든 (i, j)에 대한 board[i][j]의 합을 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ board의 길이 ≤ 100
- 1 ≤ board[i]의 길이 ≤ 100
  - 1 ≤ board[i][j] ≤ 10,000
  - 모든 board[i]의 길이는 같습니다.
- 0 ≤ k < board의 길이 + board[i]의 길이

### 입출력 예

| board                                        | k   | result |
| -------------------------------------------- | --- | ------ |
| [[0, 1, 2], [1, 2, 3], [2, 3, 4], [3, 4, 5]] | 2   | 8      |

# 🧐 접근

중첩반복문을 사용하여 순회하자

```java
class Solution {
    public int solution(int[][] board, int k) {
        int answer = 0;
        int idx = board.length;
        for(int i = 0; i < idx; i++) {
            for(int j = 0; j < board[i].length; j++) {
                if(i + j <= k) answer +=board[i][j];
            }
        }
        return answer;
    }
}
```

# 💡 풀이

2차원 배열을 중첩반복문으로 순회하며 조건에 맞는 좌표의 값을 answer에 더해줌

# 📘 그 외의 풀이

### 1. Stream사용

> 💡 Stream으로 순회하며 filter로 해당 조건 만족시 sum() 메서드 수행

```java
import java.util.stream.IntStream;

class Solution {
    public static int solution(int[][] board, int k) {
        return IntStream.range(0, board.length).filter(i -> i <= k).map(i -> IntStream.range(0, board[i].length).filter(j -> j <= k - i).map(j -> board[i][j]).sum()).sum();
    }
}
```
