# 공백으로 구분하기 2

## 📌 문제 설명

단어가 공백 한 개 이상으로 구분되어 있는 문자열 my_string이 매개변수로 주어질 때, my_string에 나온 단어를 앞에서부터 순서대로 담은 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- my_string은 영소문자와 공백으로만 이루어져 있습니다.
- 1 ≤ my_string의 길이 ≤ 1,000
- my_string의 맨 앞과 맨 뒤에도 공백이 있을 수 있습니다.
- my_string에는 단어가 하나 이상 존재합니다.

### 입출력 예

| my_string           | result               |
| ------------------- | -------------------- |
| " i    love  you"   | ["i", "love", "you"] |
| "    programmers  " | ["programmers"]      |

# 🧐 접근

`trim()`과 `split()`메소드 사용

```java
class Solution {
    public String[] solution(String my_string) {
        return my_string.trim().split("\\s+");
    }
}
```

# 💡 풀이

`trim()`을 사용해서 문자열 앞, 뒤의 공백을 없애고,
`split()`에 `\\s+`를 사용해서 하나 이상의 공백을 기준으로 문자열을 분리한다.

# 📘 그 외의 풀이

### 1. 정규표현식

> 💡 정규표현식을 사용해서도 하나 이상의 공백을 표기할 수 있다.

```java
class Solution {
    public String[] solution(String my_string) {
        return my_string.trim().split("[ ]+");
    }
}
```