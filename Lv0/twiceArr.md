# 배열 두 배 만들기

## 📌 문제 설명

정수 배열 numbers가 매개변수로 주어집니다. numbers의 각 원소에 두배한 원소를 가진 배열을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- -10,000 ≤ numbers의 원소 ≤ 10,000
- 1 ≤ numbers의 길이 ≤ 1,000


### 입출력 예
| numbers                   | result                     |
| ------------------------- | -------------------------- |
| [1, 2, 3, 4, 5]           | [2, 4, 6, 8, 10]           |
| [1, 2, 100, -99, 1, 2, 3] | [2, 4, 200, -198, 2, 4, 6] |

# 🧐 접근

스트림을 생성해서 각 값에 두배를 해주자

```java
import java.util.Arrays;
class Solution {
    public int[] solution(int[] numbers) {
        return Arrays.stream(numbers)
            .map(e -> e * 2)
            .toArray();
    }
}
```

# 💡 풀이

스트림을 생성한 후 각 스트림에 2를 곱해준다.

# 📘 그 외의 풀이

###  =============