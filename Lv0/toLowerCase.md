# 소문자로 바꾸기

## 📌 문제 설명

알파벳으로 이루어진 문자열 myString이 주어집니다. 모든 알파벳을 소문자로 변환하여 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ myString의 길이 ≤ 100,000
  - myString은 알파벳으로 이루어진 문자열입니다.

### 입출력 예

| myString  | result    |
| --------- | --------- |
| "aBcDeFg" | "abcdefg" |
| "aaa"     | "aaa"     |

# 🧐 접근

`toLowerCase()`사용

```java
class Solution {
    public String solution(String myString) {
        return myString.toLowerCase();
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### ==================