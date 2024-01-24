# 접미사 배열

## 📌 문제 설명

어떤 문자열에 대해서 접미사는 특정 인덱스부터 시작하는 문자열을 의미합니다. 예를 들어, "banana"의 모든 접미사는 "banana", "anana", "nana", "ana", "na", "a"입니다.
문자열 my_string이 매개변수로 주어질 때, my_string의 모든 접미사를 사전순으로 정렬한 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- my_string은 알파벳 소문자로만 이루어져 있습니다.
- 1 ≤ my_string의 길이 ≤ 100

### 입출력 예

| my_String     | result             |
| ------------- | ------------------ |
| "banana"      | 	["a", "ana", "anana", "banana", "na", "nana"] |
| "programmers" | ["ammers", "ers", "grammers", "mers", "mmers", "ogrammers", "programmers", "rammers", "rogrammers", "rs", "s"] |

# 🧐 접근

`substring()`시용해서 접미사를 추출하자

```java
import java.util.Arrays;
class Solution {
    public String[] solution(String my_string) {
        String[] answer = new String[my_string.length()];
        for (int i = 0; i < my_string.length(); i++) answer[i] = my_string.substring(i);
        Arrays.sort(answer);
        return answer;
    }
}
```

# 💡 풀이

`substring()`을 사용해서 문자열 객체`my_string`의 접미사들을 추출한 후 `sort()`메소드를 사용해 사전 순으로 정렬한다.

# 📘 그 외의 풀이

### ===============