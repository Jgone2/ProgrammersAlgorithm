# l로 만들기

## 📌 문제 설명

알파벳 소문자로 이루어진 문자열 myString이 주어집니다. 알파벳 순서에서 "l"보다 앞서는 모든 문자를 "l"로 바꾼 문자열을 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ myString ≤ 100,000
  - myString은 알파벳 소문자로 이루어진 문자열입니다.

### 입출력 예

| myString     | result       |
| ------------ | ------------ |
| "abcdevwxyz" | "lllllvwxyz" |
| "jjnnllkkmm" | "llnnllllmm" |

# 🧐 접근

조건문을 사용해서 비교

```java
class Solution {
    public String solution(String myString) {
        StringBuilder sb = new StringBuilder();
        for(char c : myString.toCharArray()) {
            if (c < 'l') sb.append('l');
            else sb.append(c);
        }
        return sb.toString();
    }
}
```

# 💡 풀이

조건문을 사용해서 'l'보다 앞서는 알파벳일 시 'l'을 추가하고 나머지 알파벳일 시 알파벳 그대로 추가

# 📘 그 외의 풀이

### 1. 정규표현식

> 💡 정규표현식 `[^l-z]`를 사용해 l-z를 제외한 알파벳일 시 `l`로 변경

```java
class Solution {
    public String solution(String myString) {
        return myString.replaceAll("[^l-z]", "l");
    }
}
```