# 뒤에서 5등까지

## 📌 문제 설명

정수로 이루어진 리스트 num_list가 주어집니다. num_list에서 가장 작은 5개의 수를 오름차순으로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 6 ≤ num_list의 길이 ≤ 30
- 1 ≤ num_list의 원소 ≤ 100

### 입출력 예
| num_list                   | result             |
| -------------------------- | ------------------ |
| [12, 4, 15, 46, 38, 1, 14] | [1, 4, 12, 14, 15] |

# 🧐 접근

stream을 사용해서 원본배열에서 연산하자.

```java
import java.util.Arrays;

class Solution {
    public int[] solution(int[] num_list) {
        return Arrays.stream(num_list)
            .sorted()
            .limit(5)
            .toArray();
    }
}
```

# 💡 풀이

`stream()`의 메소드들을 사용해서 `sorted()`를 사용해서 오름차순으로 배열을 정렬하고,
`limit()`를 사용해 앞의 n개 요소를 추출해서 배열로 변환

메모리 효율성 측면까지 생각하면 iter문을 사용하는게 좋아보이긴하다.

# 📘 그 외의 풀이

###  ================