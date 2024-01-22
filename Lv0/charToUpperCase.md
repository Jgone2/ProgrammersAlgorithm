# 특정한 문자를 대문자로 바꾸기

## 📌 문제 설명

영소문자로 이루어진 문자열 my_string과 영소문자 1글자로 이루어진 문자열 alp가 매개변수로 주어질 때, my_string에서 alp에 해당하는 모든 글자를 대문자로 바꾼 문자열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 1,000

### 입출력 예

| my_string         | n   | result        |
| ----------------- | --- | ------------- |
| "programmers"     | "p" | "Programmers" |
| "lowercase"       | "x" | "lowercase"   |

# 🧐 접근

`replace()`사용

```java
class Solution {
    public String solution(String my_string, String alp) {
        char c = alp.charAt(0);
        return my_string.replace(c, Character.toUpperCase(c));
    }
}
```

```java
class Solution {
    public String solution(String my_string, String alp) {
        return my_string.replace(alp, alp.toUpperCase());
    }
}
```

# 💡 풀이

`replace()`메소드를 사용해서 alp를 대문자로 변환

# 📘 그 외의 풀이

### ==================