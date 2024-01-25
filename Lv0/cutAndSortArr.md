# 문자열 잘라서 정렬하기

## 📌 문제 설명

문자열 myString이 주어집니다. "x"를 기준으로 해당 문자열을 잘라내 배열을 만든 후 사전순으로 정렬한 배열을 return 하는 solution 함수를 완성해 주세요.

단, 빈 문자열은 반환할 배열에 넣지 않습니다.

### 제한 조건

- 1 ≤ myString ≤ 100,000
  - myString은 알파벳 소문자로 이루어진 문자열입니다.

### 입출력 예

| myString        | result                  |
| --------------- | ----------------------- |
| "axbxcxdx"      | ["a","b","c","d"]       |
| "dxccxbbbxaaaa" | ["aaaa","bbb","cc","d"] |

# 🧐 접근

`split()`메소드로 배열화 한  `isEmpty()`메소드를 사용해 빈 값을 제외한 값을 배열에 추가하자

```java
import java.util.Arrays;
import java.util.ArrayList;
class Solution {
    public String[] solution(String myString) {
        String[] split = myString.split("x");
        ArrayList<String> list = new ArrayList<>();
        for (String str : split) {
            if (!str.isEmpty()) {
                list.add(str);
            }
        }
        String[] answer = list.toArray(String[]::new);
        Arrays.sort(answer);
        return answer;
    }
}
```

# 💡 풀이

`split()`메소드로 문자열`myString`을 `"x"`를 기준으로 분리해 배열화 한다.
이후 `List`를 생성하여 문자열에서 빈 값을 제외한 값을 리스트에 추가하고 배열로 변환 후 정렬한다.

# 📘 그 외의 풀이

### ==========