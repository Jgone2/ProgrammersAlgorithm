# 배열 자르기

## 📌 문제 설명

정수 배열 numbers와 정수 num1, num2가 매개변수로 주어질 때, numbers의 num1번 째 인덱스부터 num2번째 인덱스까지 자른 정수 배열을 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 2 ≤ numbers의 길이 ≤ 30
- 0 ≤ numbers의 원소 ≤ 1,000
- 0 ≤num1 < num2 < numbers의 길이

### 입출력 예

| numbers         | num1 | num2	| result    |
| --------------- | ---- | ---- | --------- |
| [1, 2, 3, 4, 5] |	1    | 3    | [2, 3, 4] |
| [1, 3, 5]       |	1	 | 2	| [3, 5]    |

# 🧐 접근

배열복사로 해결

```java
import java.util.Arrays;
class Solution {
    public int[] solution(int[] numbers, int num1, int num2) {
        return Arrays.copyOfRange(numbers, num1, num2 + 1);
    }
}
```

# 💡 풀이

배열 복사를 통해 원하는 만큼만 복사해서 반환

# 📘 그 외의 풀이

### 1. for문 사용

> 💡 반복문을 통해 잘라 낼 부분만 배열`answer`에 값을 할당해준다.

```java
class Solution {
    public int[] solution(int[] numbers, int num1, int num2) {
        int[] answer = new int[num2 - num1 + 1];

        for (int i = num1; i <= num2; i++) {
            answer[i-num1] = numbers[i];
        }

        return answer;
    }
}
```