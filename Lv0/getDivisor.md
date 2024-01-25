# 약수 구하기

## 📌 문제 설명

정수 n이 매개변수로 주어질 때, n의 약수를 오름차순으로 담은 배열을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ n ≤ 10,000

### 입출력 예

| n  | result                     |
| -- | -------------------------- |
| 24 | [1, 2, 3, 4, 6, 8, 12, 24] |
| 29 | [1, 29]                    |

# 🧐 접근

1부터 해당 수 까지 나머지 연산을 사용했을 때 나머지가 0인 수 추출

```java
import java.util.ArrayList;
class Solution {
    public int[] solution(int n) {
        ArrayList<Integer> list = new ArrayList<>();
        for (int i = 1; i <= n; i++) {
            if (n % i == 0) list.add(i);
        }
        int[] answer = new int[list.size()];
        for (int i = 0; i < answer.length; i++) answer[i] = list.get(i);
        return answer;
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### =============