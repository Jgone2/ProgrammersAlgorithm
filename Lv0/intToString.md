# 문자열로 변환

## 📌 문제 설명

정수 n이 주어질 때, n을 문자열로 변환하여 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ n ≤ 10000

### 입출력 예

| n    | result |
| ---- | ------ |
| 123  | "123"  |
| 2573 | "2573" |

# 🧐 접근

`String.valueOf()`사용해서 문자열 객체로 변환

```java
class Solution {
    public String solution(int n) {
        return String.valueOf(n);
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### ===================