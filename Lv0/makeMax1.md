# 최댓값 만들기(1)

## 📌 문제 설명

정수 배열 numbers가 매개변수로 주어집니다. numbers의 원소 중 두 개를 곱해 만들 수 있는 최댓값을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 0 ≤ numbers의 원소 ≤ 10,000
- 2 ≤ numbers의 길이 ≤ 100

### 입출력 예

| numbers               | result |
| --------------------- | ------ |
| [1, 2, 3, 4, 5]       | 20     |
| [0, 31, 24, 10, 1, 9] | 744    |

# 🧐 접근

배열의 정렬로 가장 큰 수 두 값을 구하자

```java
import java.util.Arrays;
class Solution {
    public int solution(int[] numbers) {
        Arrays.sort(numbers);
        return numbers[numbers.length - 1] * numbers[numbers.length - 2];
    }
}
```

# 💡 풀이

배열의 정렬로 가장 큰 두 수를 구하고 연산.

# 📘 그 외의 풀이

### 1. Stream 사용

> 💡

```java
import java.util.Arrays;
import java.util.Comparator;

class Solution {
    public int solution(int[] numbers) {
        return Arrays.stream(numbers)
                .boxed()
                .sorted(Comparator.reverseOrder())
                .limit(2L)
                .reduce(1, Math::multiplyExact);
    }
}
```

### 2. 선택정렬

> 💡

```java
class Solution {
    public int solution(int[] numbers) {
        int answer = 0;

        for (int i = 0; i < numbers.length; i++) {
            for (int j = i; j < numbers.length; j++) {
                if (numbers[j] < numbers[i]) {
                    int temp = numbers[i];
                    numbers[i] = numbers[j];
                    numbers[j] = temp;
                }
            }
        }

        answer = numbers[numbers.length - 2] * numbers[numbers.length - 1];

        return answer;
    }
}
```
