# 배열의 유사도

## 📌 문제 설명

두 배열이 얼마나 유사한지 확인해보려고 합니다. 문자열 배열 s1과 s2가 주어질 때 같은 원소의 개수를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ s1, s2의 길이 ≤ 100
- 1 ≤ s1, s2의 원소의 길이 ≤ 10
- s1과 s2의 원소는 알파벳 소문자로만 이루어져 있습니다
- s1과 s2는 각각 중복된 원소를 갖지 않습니다.


### 입출력 예
| s1              | s2                          | result |
| --------------- | --------------------------- | ------ |
| ["a", "b", "c"] | ["com", "b", "d", "p", "c"] | 2      |
| ["n", "omg"]    | ["m", "dot"]                | 0      |

# 🧐 접근

Map을 사용해서 key, value로 비교하자

```java
import java.util.HashMap;
import java.util.Map;

class Solution {
    public int solution(String[] s1, String[] s2) {
        int cnt = 0;
        Map<String, String> map = new HashMap<String, String>();
        for (String s : s1) map.put(s, s);
        for (String s : s2) if (map.containsKey(s)) cnt++;
        return cnt;
    }
}
```

# 💡 풀이

HashMap을 사용해서 배열`s1`을 key값과 value값으로 할당하고,
배열`s2`의 각각의 문자열을 HashMap의 key로 존재하는지 확인.

# 📘 그 외의 풀이

###  =============