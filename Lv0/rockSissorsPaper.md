# 가위 바위 보

## 📌 문제 설명

가위는 2 바위는 0 보는 5로 표현합니다. 가위 바위 보를 내는 순서대로 나타낸 문자열 rsp가 매개변수로 주어질 때, rsp에 저장된 가위 바위 보를 모두 이기는 경우를 순서대로 나타낸 문자열을 return하도록 solution 함수를 완성해보세요.

### 제한 조건

- 0 < rsp의 길이 ≤ 100
- rsp와 길이가 같은 문자열을 return 합니다.
- rsp는 숫자 0, 2, 5로 이루어져 있습니다.

### 입출력 예

| rsp   | result |
| ----- | ------ |
| "2"   | "0"    |
| "205" | "052"  |

# 🧐 접근

각 조건에 맞는 값을 넣자

```java
class Solution {
    public String solution(String rsp) {
        StringBuilder sb = new StringBuilder();
        for (char c : rsp.toCharArray()) {
            if (c == '2') sb.append("0");
            else if (c == '0') sb.append("5");
            else sb.append("2");
        }
        return sb.toString();
    }
}
```

# 💡 풀이

반복문을 수행하면서 각 조건에서 이기는 경우의 수를 추가

# 📘 그 외의 풀이

### 1. HashMap

> 💡 HashMap으로 key와 value를 설정 후 반복문을 통해 각 key값에 해당하는 value값을 answer에 추가해주고 있다.


```java
import java.util.HashMap;
import java.util.Map;

class Solution {
    public String solution(String rsp) {
        //2 - 가위, 0 - 바위, 5 - 보
        Map<String, String> winNumbers = new HashMap<>();
        winNumbers.put("2", "0");
        winNumbers.put("0", "5");
        winNumbers.put("5", "2");

        StringBuilder answer = new StringBuilder();

        for (int i = 0; i < rsp.length(); i++) {
            answer.append(winNumbers.get(rsp.substring(i, i+1)));
        }

        return answer.toString();
    }
}
```