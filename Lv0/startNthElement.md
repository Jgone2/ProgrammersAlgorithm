# n번째 원소부터

## 📌 문제 설명

정수 리스트 num_list와 정수 n이 주어질 때, n 번째 원소부터 마지막 원소까지의 모든 원소를 담은 리스트를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 2 ≤ num_list의 길이 ≤ 30
- 1 ≤ num_list의 원소 ≤ 9
- 1 ≤ n ≤ num_list의 길이

### 입출력 예

| num_list	      | n |	result       |
| --------------- | - | ------------ |
| [2, 1, 6]       |	3 |	[6]          |
| [5, 2, 1, 7, 5] |	2 |	[2, 1, 7, 5] |

# 🧐 접근

배열복사를 통해 실행

```java
import java.util.Arrays;
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = new int[num_list.length - (n - 1)];
        answer = Arrays.copyOfRange(num_list, n - 1, num_list.length);
        return answer;
    }
}
```

# 💡 풀이

배열`answer`의 길이를 num_list의 길이에서 n을 뺀값으로 지정하고,
배열복사를 통해 n - 1인덱스부터 마지막원소까지 복사.



> 💡 배열복사
> 배열 복사를 수행할 때는 복사받을 배열의 크기를 지정하지 않아도 된다고 한다.
바로 리턴도 가능

```java
import java.util.Arrays;
class Solution {
    public int[] solution(int[] num_list, int n) {
        return Arrays.copyOfRange(num_list, n - 1, num_list.length);
    }
}
```

# 📘 그 외의 풀이

### ==================