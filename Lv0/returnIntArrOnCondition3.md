# 조건에 맞게 수열 변환하기 3

## 📌 문제 설명

정수 배열 arr와 자연수 k가 주어집니다.
만약 k가 홀수라면 arr의 모든 원소에 k를 곱하고, k가 짝수라면 arr의 모든 원소에 k를 더합니다.
이러한 변환을 마친 후의 arr를 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ arr의 길이 ≤ 1,000,000
  - 1 ≤ arr의 원소의 값 ≤ 100
- 1 ≤ k ≤ 100

### 입출력 예

| arr                    | k | result                   |
| ---------------------- | - | ------------------------ |
| [1, 2, 3, 100, 99, 98] | 3 | [3, 6, 9, 300, 297, 294] |
| [1, 2, 3, 100, 99, 98] | 2 | [3, 4, 5, 102, 101, 100] |

# 🧐 접근

2개의 조건에 따라 다르게 출력되니 삼항연산자를 사용해보자

```java
import java.util.Arrays;

class Solution {
    public int[] solution(int[] arr, int k) {
        return (k % 2 == 0) ? 
            Arrays.stream(arr).map(n -> n + k).toArray()
        : Arrays.stream(arr).map(n -> n * k).toArray();
    }
}
```

# 💡 풀이

삼항 연산자를 사용해서 `k`가 짝수일 때를 조건식으로 걸고 참일때와 거짓일 때를 `Stream()`을 활용해서 배열의 각 값에 연산을 수행하고 배열로 반환

# 📘 그 외의 풀이

### 1. `Stream()`내에서 삼항 연산자 사용

> 💡 `Stream()`내에서 삼항 연산자를 사용해서 풀이.
> 📒 이렇게 사용하면 내 코드에서 발생했던 코드 중복을 피할 수 있다.

```java
class Solution {
    public int[] solution(int[] arr, int k) {
        return Arrays.stream(arr).map(operand -> k % 2 == 0 ? operand + k : operand * k).toArray();
    }
}
```