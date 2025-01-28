# 문자열 정렬하기 (2)

## 📌 문제 설명

영어 대소문자로 이루어진 문자열 my_string이 매개변수로 주어질 때, my_string을 모두 소문자로 바꾸고 알파벳 순서대로 정렬한 문자열을 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 100

### 입출력 예

| my_string | result   |
| --------- | -------- |
| "Bcad"    | "abcd"   |
| "heLLo"   | "ehllo"  |
| "Python"  | "hnopty" |

# 🧐 접근

Arrays.sort를 사용하자

```java
import java.util.Arrays;

class Solution {
    public String solution(String my_string) {
        char[] charArray = my_string.toLowerCase().toCharArray();
        Arrays.sort(charArray);

        return new String(charArray);
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### 1. Stream사용

> 💡 재정렬을 위해 split("")을 사용해 문자를 분리 후 정렬하여 `Collectors.joining()`을 사용해 하나의 문자열로 재조합

```java
import java.util.*;
import java.util.stream.Collectors;

class Solution {
    public String solution(String myString) {
        return Arrays.stream(myString.toLowerCase(Locale.ROOT).split("")).sorted().collect(Collectors.joining());
    }
}
```
