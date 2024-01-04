# 배열 뒤집기

## 📌 문제 설명

정수가 들어 있는 배열 num_list가 매개변수로 주어집니다. num_list의 원소의 순서를 거꾸로 뒤집은 배열을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

-  ≤ num_list의 길이 ≤ 1,000
- 0 ≤ num_list의 원소 ≤ 1,000

### 입출력 예

| num_list              | result                |
| --------------------- | --------------------- |
| [1, 2, 3, 4, 5]       | [5, 4, 3, 2, 1]       |
| [1, 1, 1, 1, 2]       | [2, 1, 1, 1, 1]       |
| [1, 0, 1, 1, 1, 3, 5] | [5, 3, 1, 1, 1, 0, 1] |

# 🧐 접근

양쪽 끝에서 중간으로 오며 뒤집기

```java
class Solution {
    public int[] solution(int[] num_list) {
        int left = 0;
        int right = num_list.length - 1;
        while (left < right) {
            int tmp = num_list[left];
            num_list[left] = num_list[right];
            num_list[right] = tmp;
            left++;
            right--;
        }
        return num_list;
    }
}
```

# 💡 풀이

배열의 시작점과 배열의 마지막에서 서로 두 값을 뒤집으며 중앙에서 만나기 직전까지 뒤집기 연산을 수행

# 📘 그 외의 풀이

###  1. Collection 사용

> 💡 Collection을 사용해서 `reverse()`메소드를 사용
> ❗️ 시간복잡도는 여전히 O(n)이지만 추가적인 List와 Steam객체의 생성으로 메모리 사용량이 증가

```java
import java.util.Collections;
import java.util.List;
import java.util.stream.Collectors;
import java.util.Arrays;

class Solution {
    public int[] solution(int[] numList) {
        List<Integer> list = Arrays.stream(numList).boxed().collect(Collectors.toList());

        Collections.reverse(list);
        return list.stream().mapToInt(Integer::intValue).toArray();
    }
}
```