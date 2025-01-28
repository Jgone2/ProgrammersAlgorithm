# 글자 지우기

## 📌 문제 설명

문자열 my_string과 정수 배열 indices가 주어질 때, my_string에서 indices의 원소에 해당하는 인덱스의 글자를 지우고 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ indices의 길이 < my_string의 길이 ≤ 100
- my_string은 영소문자로만 이루어져 있습니다
- 0 ≤ indices의 원소 < my_string의 길이
- indices의 원소는 모두 서로 다릅니다..

### 입출력 예

| my_string             | indices                      | result        |
| --------------------- | ---------------------------- | ------------- |
| "apporoograpemmemprs" | [1, 16, 6, 15, 0, 10, 11, 3] | "programmers" |

# 🧐 접근

indices를 오름차순 정렬하고 문자열의 길이만큼 반복문을 순회하자.

```java
import java.util.*;

class Solution {
    public String solution(String my_string, int[] indices) {
        StringBuilder sb = new StringBuilder();
        Arrays.sort(indices);
        int idx = 0;
        for(int i = 0; i < my_string.length(); i++) {
            if(idx < indices.length && indices[idx] == i) {
                idx++;
            } else {
                sb.append(my_string.charAt(i));
            }
        }
        return sb.toString();
    }
}
```

# 💡 풀이

문자열 순차적 순회를 위해 배열 `indicies`를 오름차순 정렬하고 따로 인덱스(`idx`)를 주어 조건식을 검사. 조건식을 검사할때 조건식이 참일 때만 인덱스를 `+1`해준다.

# 📘 그 외의 풀이

### 1. indices 크기로 순회

> 💡 indices배열의 길이로 순회하며 해당 인덱스에 해당하는 값을 `""` 처리 후 문자열로 재조합

```java
class Solution {

    public String solution(String my_string, int[] indices) {
        String answer = "";
        String[] tmp = my_string.split("");

        for (int i = 0; i < indices.length; i++) {
            tmp[indices[i]] = "";
        }

        for (String x : tmp) {
            answer += x;
        }
        return answer;
    }
}
```

```java
class Solution {
    public String solution(String my_string, int[] indices) {
        String[] str = my_string.split("");
        for (int i=0;i<indices.length;i++) str[indices[i]] = "";
        return String.join("",str);
    }
}
```
