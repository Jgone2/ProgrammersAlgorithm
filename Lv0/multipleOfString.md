# 문자열 곱하기

## 📌 문제 설명

문자열 my_string과 정수 k가 주어질 때, my_string을 k번 반복한 문자열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 100
- my_string은 영소문자로만 이루어져 있습니다.
- 1 ≤ k ≤ 100


### 입출력 예

| myString  | k  | result                                     |
| --------- | -- | ------------------------------------------ |
| "string"  | 3  | "stringstringstring"                       |
| "love"    | 10 | "lovelovelovelovelovelovelovelovelovelove" |

# 🧐 접근

`repeat()`사용

```java
class Solution {
    public String solution(String my_string, int k) {
        return my_string.repeat(k);
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### ==================