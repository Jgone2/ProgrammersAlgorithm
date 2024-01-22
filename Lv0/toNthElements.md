# n번째 원소까지

## 📌 문제 설명

정수 리스트 num_list와 정수 n이 주어질 때, num_list의 첫 번째 원소부터 n 번째 원소까지의 모든 원소를 담은 리스트를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 2 ≤ num_list의 길이 ≤ 30
- 1 ≤ num_list의 원소 ≤ 9
- 1 ≤ n ≤ num_list의 길이 ___


### 입출력 예

| num_list        | n | result    |
| --------------- | - | --------- |
| [2, 1, 6]       | 1 | [2]       |
| [5, 2, 1, 7, 5] | 3 | [5, 2, 1] |

# 🧐 접근

`copyOfRange()`를 사용해 배열복사

```java
import java.util.Arrays;
class Solution {
    public int[] solution(int[] num_list, int n) {
        return Arrays.copyOfRange(num_list, 0, n);
    }
}
```

# 💡 풀이

`copyOfRange()`를 사용하여 해당범위까찌 복사 후 반환

# 📘 그 외의 풀이

### ==================