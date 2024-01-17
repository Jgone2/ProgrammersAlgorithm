# 제곱수 판별하기

## 📌 문제 설명

어떤 자연수를 제곱했을 때 나오는 정수를 제곱수라고 합니다. 정수 n이 매개변수로 주어질 때, n이 제곱수라면 1을 아니라면 2를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ n ≤ 1,000,000

### 입출력 예

| n   | result |
| --- | ------ |
| 144 | 1      |
| 976 | 2      |

# 🧐 접근

제곱근을 구해서 제곱

```java
class Solution {
    public int solution(int n) {
        int sqrt = (int)Math.sqrt(n);
        return sqrt * sqrt == n ? 1 : 2;
    }
}
```

# 💡 풀이

`sqrt()`를 사용해서 제곱근을 구하고,
제곱근을 제곱해서 원래 정수와 값이 같은지 판별

# 📘 그 외의 풀이

### 1. 나머지 연산자 사용

> 💡 n과 n의 제곱근을 사용해 나머지 연산자로 연산 후 제곱수를 판별

```java
class Solution {
    public int solution(int n) {
        if (n % Math.sqrt(n) == 0) {
            return 1;
        } else {
            return 2;
        }
    }
}
```