# n의 배수

## 📌 문제 설명

정수 num과 n이 매개 변수로 주어질 때, num이 n의 배수이면 1을 return n의 배수가 아니라면 0을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 2 ≤ num ≤ 100
- 2 ≤ n ≤ 9

### 입출력 예

| num | n | result |
| --- | - | ------ |
| 98  | 2 | 1      |
| 34  | 2 | 0      |

# 🧐 접근

삼항연산자 사용

```java
class Solution {
    public int solution(int num, int n) {
        return num % n == 0 ? 1 : 0 ;
    }
}
```

# 💡 풀이

삼항연산자를 사용해서 조건에 부합하는 값을 반환.

# 📘 그 외의 풀이

### ==================