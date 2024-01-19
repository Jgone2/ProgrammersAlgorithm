# 접두사인지 확인하기

## 📌 문제 설명

어떤 문자열에 대해서 접두사는 특정 인덱스까지의 문자열을 의미합니다. 예를 들어, "banana"의 모든 접두사는 "b", "ba", "ban", "bana", "banan", "banana"입니다.
문자열 my_string과 is_prefix가 주어질 때, is_prefix가 my_string의 접두사라면 1을, 아니면 0을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 100
- 1 ≤ is_prefix의 길이 ≤ 100
- my_string과 is_prefix는 영소문자로만 이루어져 있습니다.

### 입출력 예

| my_string | is_prefix | result |
| --------- | --------- | ------ |
| "banana"  | "ban"     | 1      |
| "banana"  | "nan"     | 0      |
| "banana"  | "abcd"    | 0      |
| "banana"  | "bananan" | 0      |

# 🧐 접근

`startsWith()`메소드 사용

```java
class Solution {
    public int solution(String my_string, String is_prefix) {
        return my_string.startsWith(is_prefix) ? 1 : 0 ;
    }
}
```

# 💡 풀이

`startsWith()`메소드를 사용해서 해당 문자열로 시작하는지 알 수 있다.
반복문을 통해서 수행하면 다음처럼 작성할 수도 있다.

```java
class Solution {
    public int solution(String my_string, String is_prefix) {
        if(is_prefix.length() > my_string.length()) return 0;
        for(int i = 0; i < is_prefix.length(); i++) {
            if(my_string.charAt(i) != is_prefix.charAt(i)) return 0;
        }
        return 1;
    }
}
```

# 📘 그 외의 풀이

### 1. indexOf()

> 💡 `indexOf()`메소드를 사용해서 해당 문자열에 속하는지 비교해서, 0번쨰 인덱스부터 시작하는지 확인해보면 접두사인지 아닌지 확인이 가능하다.

```java
class Solution {
    public int solution(String my_string, String is_prefix) {
        int answer = 0;
        if(my_string.indexOf(is_prefix) == 0){
            answer = 1;
        }
        return answer;
    }
}
```

###  2. anyMatch

> 💡 `anyMatch()`메소드를 사용하면 첫 인덱스부터 매개변수 내의 문자열과 비교해서 일치하는지 확인한다고 한다는걸 새롭게 알게 됐다.
> 🎉 `rangeClosed()`에서 `myString.length() -> isPrefix.length()`로 변경해도 무관하다.

```java
import java.util.*;
import java.util.stream.*;

class Solution {
    public int solution(String myString, String isPrefix) {
        return IntStream.rangeClosed(0, myString.length())
            .mapToObj(i -> myString.substring(0, i))
            .anyMatch(s -> s.equals(isPrefix)) ? 1 : 0;
    }
}
```