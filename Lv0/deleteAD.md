# ad 제거하기

## 📌 문제 설명

문자열 배열 strArr가 주어집니다. 배열 내의 문자열 중 "ad"라는 부분 문자열을 포함하고 있는 모든 문자열을 제거하고 남은 문자열을 순서를 유지하여 배열로 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ strArr의 길이 ≤ 1,000
  - 1 ≤ strArr의 원소의 길이 ≤ 20
  - strArr의 원소는 알파벳 소문자로 이루어진 문자열입니다.

### 입출력 예

| strArr                        | result                        |
| ----------------------------- | ----------------------------- |
| ["and","notad","abcd"]        | ["and","abcd"]                |
| ["there","are","no","a","ds"] | ["there","are","no","a","ds"] |

# 🧐 접근

`ArrayList`에 값 추가 후 배열로 전환

```java
import java.util.ArrayList;
import java.util.List;
class Solution {
    public String[] solution(String[] strArr) {
        List<String> list = new ArrayList<>();
        for (String str : strArr) {
            if (!str.contains("ad")) list.add(str);
        }
        String[] answer = list.toArray(String[]::new);
        return answer;
    }
}
```

# 💡 풀이

배열`answer`의 크기를 예측할 수 없기에 ArrayList를 생성한 후 조건에 부합할 시 그 값을 list에 추가한 후 배열로 변환

# 📘 그 외의 풀이

### ==================