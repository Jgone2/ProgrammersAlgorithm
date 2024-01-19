# 공배수

## 📌 문제 설명

정수 number와 n, m이 주어집니다. number가 n의 배수이면서 m의 배수이면 1을 아니라면 0을 return하도록 solution 함수를 완성해주세요.
### 제한 조건

- 10 ≤ number ≤ 100
- 2 ≤ n, m < 10

### 입출력 예

| number | n  | m | result |
| ------ | -- | - | ------ |
| 60     | 2  | 3 | 1      |
| 55     | 10 | 5 | 0      |

# 🧐 접근

삼항연산자 사용

```java
class Solution {
    public int solution(int number, int n, int m) {
        return (number % n == 0) && (number % m == 0) ? 1 : 0 ;
    }
}
```

# 💡 풀이

number를 n과 m으로 각각 나머지 연산자를 사용해서 두 조건에서 모두 나머지가 0일 시,
조건을 부합하게된다.

# 📘 그 외의 풀이

### ==================