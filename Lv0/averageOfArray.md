# 배열의 평균값

## 📌 문제 설명

정수 배열 numbers가 매개변수로 주어집니다. numbers의 원소의 평균값을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 0 ≤ numbers의 원소 ≤ 1,000
- 1 ≤ numbers의 길이 ≤ 100
- 정답의 소수 부분이 .0 또는 .5인 경우만 입력으로 주어집니다.

### 입출력 예

| numbers                                      | result |
| -------------------------------------------- | ------ |
| [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]              | 5.5    |
| [89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99] | 94.0   |

# 🧐 접근

반복문을 통해서 배열내의 원소값들을 더하기

```java
class Solution {
    public double solution(int[] numbers) {
        double answer = 0;
        for(int num : numbers) {
            answer += num;
        }
        answer /= numbers.length;
        return answer;
    }
}
```

# 💡 풀이

for 반복문을 사용해서 배열의 원소값들을 answer에 더해주고, 배열의 길이로 나누어 평균을 구함

# 📘 그 외의 풀이

### 1. stream 사용

> 💡 stream을 사용해서 배열의 원소값들을 더하고, 평균을 구함

```java
import java.util.Arrays;

class Solution {
    public double solution(int[] numbers) {
        return Arrays.stream(numbers).average().orElse(0);
    }
}
```
