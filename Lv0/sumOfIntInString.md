# 문자열 정수의 합

## 📌 문제 설명

한 자리 정수로 이루어진 문자열 num_str이 주어질 때, 각 자리수의 합을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 3 ≤ num_str ≤ 100

### 입출력 예

| num_str     | result |
| ----------- | ------ |
| "123456789" | 45     |
| "1000000"   | 1      |

# 🧐 접근

`Character.getNumericValue()`메소드 사용

```java
class Solution {
    public int solution(String num_str) {
        int answer = 0;
        for (char c : num_str.toCharArray()) {
            answer += Character.getNumericValue(c);
        }
        return answer;
    }
}
```

# 💡 풀이

반복문을 수행하며 각 인덱스의 문자를 `Character.getNumericValue()`를 사용하여 정수화 한 뒤 answer에 더하기 연산 실행

이전 문제 풀이에서 `ASCII`를 사용해 풀이한 것을 적용해보면 다음과 같이 풀이할 수 있다.
```java
class Solution {
    public int solution(String num_str) {
        int answer = 0;
        for (char c : num_str.toCharArray()) {
            answer += c - 48;
        }
        return answer;
    }
}
```

# 📘 그 외의 풀이

### 1. Stream()

> 💡 String.chars()로 문자열의 문자를 스트림으로 변환 후 연산 수행


```java
class Solution {
    public int solution(String numStr) {
        return numStr.chars().map(c -> c - 48).sum();
    }
}

```