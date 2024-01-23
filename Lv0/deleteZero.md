# 0 떼기

## 📌 문제 설명

정수로 이루어진 문자열 n_str이 주어질 때, n_str의 가장 왼쪽에 처음으로 등장하는 0들을 뗀 문자열을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 2 ≤ n_str ≤ 10
- n_str이 "0"으로만 이루어진 경우는 없습니다.

### 입출력 예

| n_str    | result   |
| -------- | -------- |
| "0010"   | "10"     |
| "854020" | "854020" |

# 🧐 접근

정규표현식과 `replaceAll()`메소드 사용

```java
class Solution {
    public String solution(String n_str) {
        return n_str.replaceAll("^0+", "");
    }
}
```

# 💡 풀이

`replaceAll()`메소드를 사용해서 정규표현식 `"^0+"`를 사용해 문자열 시작에서 하나이상의 0으로 시작하면 `""`로 변경

# 📘 그 외의 풀이

### 1. String.valueOf(), Integer.parseInt

> 💡 정수형으로 변환을 한번 진행하여 앞의 0을 삭제

```java
class Solution {
    public String solution(String nStr) {
        return String.valueOf(Integer.parseInt(nStr));
    }
}
```

```java
class Solution {
    public String solution(String n_str) {
        return ""+Integer.parseInt(n_str);
    }
}
```