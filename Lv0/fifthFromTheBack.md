# 뒤에서 5등 위로

## 📌 문제 설명

정수로 이루어진 리스트 num_list가 주어집니다. num_list에서 가장 작은 5개의 수를 제외한 수들을 오름차순으로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 6 ≤ num_list의 길이 ≤ 30
- 1 ≤ num_list의 원소 ≤ 100

### 입출력 예

| num_list                               | result               |
| -------------------------------------- | -------------------- |
| [12, 4, 15, 46, 38, 1, 14, 56, 32, 10] | [15, 32, 38, 46, 56] |

# 🧐 접근

정렬 후 연산

```java
import java.util.Arrays;
class Solution {
    public int[] solution(int[] num_list) {
        Arrays.sort(num_list);
        int[] answer = Arrays.copyOfRange(num_list, 5, num_list.length);
        return answer;
    }
}
```

# 💡 풀이

`sort()`를 사용해 오름차순 정렬 후, 배열 복사를 통해 6번째 요소(index 5)부터 마지막 요소까지 복사 후 반환.

# 📘 그 외의 풀이

### ==================