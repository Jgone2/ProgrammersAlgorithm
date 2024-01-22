# 배열 만들기 1

## 📌 문제 설명

정수 n과 k가 주어졌을 때, 1 이상 n이하의 정수 중에서 k의 배수를 오름차순으로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ n ≤ 1,000,000
- 1 ≤ k ≤ min(1,000, n)

### 입출력 예

| n  | k | result      |
| -- | - | ----------- |
| 10 | 3 | [3, 6, 9]   |
| 15 | 5 | [5, 10, 15] |

# 🧐 접근

`rangeClosed()`사용

```java
import java.util.stream.IntStream;
class Solution {
    public int[] solution(int n, int k) {
        return IntStream.rangeClosed(k, n)
            .filter(e -> e % k == 0)
            .toArray();
    }
}
```

# 💡 풀이

`rangeClosed()`를 사용하여 범위를 k부터 n까지 지정한 후,
k의 배수를 `filter()`로 추출하여 배열화

for문을 사용하여 다음과 같이 풀이 가능
```java
class Solution {
    public int[] solution(int n, int k) {
        int[] answer = new int[n / k];
        for(int i = 0; i < answer.length; i++) {
            answer[i] = k * (i + 1);
        }
        return answer;
    }
}
```

# 📘 그 외의 풀이

### ==================