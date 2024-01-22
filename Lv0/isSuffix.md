# 접미사인지 확인하기

## 📌 문제 설명

어떤 문자열에 대해서 접미사는 특정 인덱스부터 시작하는 문자열을 의미합니다. 예를 들어, "banana"의 모든 접미사는 "banana", "anana", "nana", "ana", "na", "a"입니다.
문자열 my_string과 is_suffix가 주어질 때, is_suffix가 my_string의 접미사라면 1을, 아니면 0을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 100
- 1 ≤ is_suffix의 길이 ≤ 100
- my_string과 is_suffix는 영소문자로만 이루어져 있습니다.

### 입출력 예

| my_string | is_suffix | result |
| --------- | --------- | ------ |
| "banana"  | "ana"     | 1      |
| "banana"  | "nan"     | 0      |
| "banana"  | "wxyz"    | 0      |
| "banana"  | "abanana" | 0      |

# 🧐 접근

`endsWith()`메소드 사용

```java
class Solution {
    public int solution(String my_string, String is_suffix) {
        return my_string.endsWith(is_suffix) ? 1 : 0;
    }
}
```

# 💡 풀이

`endsWith()`메소드를 사용해서 해당 문자열로 끝나는 지 알 수 있다.
`substring()`메소드를 사용하면 다음과 같이 풀이 할 수 있다.

```java
class Solution {
    public int solution(String my_string, String is_suffix) {
        if(my_string.length() < is_suffix.length()) return 0;
        return my_string.substring(my_string.length() - is_suffix.length()).equals(is_suffix) ? 1 : 0;
    }
}
```

# 📘 그 외의 풀이

###  ===============