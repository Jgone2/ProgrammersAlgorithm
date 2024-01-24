# x 사이의 개수

## 📌 문제 설명

문자열 myString이 주어집니다. myString을 문자 "x"를 기준으로 나눴을 때 나눠진 문자열 각각의 길이를 순서대로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ myString의 길이 ≤ 100,000
  - myString은 알파벳 소문자로 이루어진 문자열입니다.

### 입출력 예

| myString       | result             |
| -------------- | ------------------ |
| "oxooxoxxox"   | [1, 2, 1, 0, 1, 0] |
| "xabcxdefxghi" | [0, 3, 3, 3]       |

# 🧐 접근

List를 사용

```java
import java.util.ArrayList;
class Solution {
    public int[] solution(String myString) {
        ArrayList<Integer> splitCount = new ArrayList<>();
        int count = 0;
        for (char c : myString.toCharArray()) {
            if (c == 'x') {
                splitCount.add(count);
                count = 0;
            } else {
                count++;
            }
        }
        splitCount.add(count);
        int[] answer = new int[splitCount.size()];
        for (int i = 0; i < answer.length; i++) answer[i] = splitCount.get(i);
        return answer;
    }
}
```

# 💡 풀이

ArrayList를 생성한 후 반복문을 통해서 c가 'x'일 때 count된 값을 `splitCount`에 추가하고'x'가 아닐 때는 count를 1씩 더해주며 연산한다

# 📘 그 외의 풀이

### 1. split(x, -1)

> 💡 split() 메소드에서 ("x", -1)이렇게 작성하면 "x"가 연속되어 있어도 무한정으로 분리가 가능하다.

```java
import java.util.*;
class Solution {
    public Integer[] solution(String myString) {
        return Arrays.stream(myString.split("x", -1)).map(String::length).toArray(Integer[]::new);
    }
}
```