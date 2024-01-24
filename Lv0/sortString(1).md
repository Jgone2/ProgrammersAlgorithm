# 문자열 정렬하기 (1)

## 📌 문제 설명

문자열 my_string이 매개변수로 주어질 때, my_string 안에 있는 숫자만 골라 오름차순 정렬한 리스트를 return 하도록 solution 함수를 작성해보세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 100
- my_string에는 숫자가 한 개 이상 포함되어 있습니다.
- my_string은 영어 소문자 또는 0부터 9까지의 숫자로 이루어져 있습니다. - - -

### 입출력 예

| my_string   | result          |
| ----------- | --------------- |
| "hi12392"   | [1, 2, 2, 3, 9] |
| "p2o4i8gj2" | [2, 2, 4, 8]    |
| "abcde0"    | [0]             |

# 🧐 접근

반복문을 순회하면서 list에 값 할당

```java
import java.util.ArrayList;
import java.util.Arrays;
class Solution {
    public int[] solution(String my_string) {
        ArrayList<Integer> list = new ArrayList<>();
        for (char c : my_string.toCharArray()) {
            if(c >= '0' && c <= '9') list.add(c - '0');
        }
        int[] answer = new int[list.size()];
        for (int i = 0; i < answer.length; i++) answer[i] = list.get(i);
        Arrays.sort(answer);
        return answer;
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### 1. replaceAll


> 💡 replaceAll 메소드를 사용해서 삭제 하면 List에서 배열로 형변환할 필요가 없어진다.

```java
import java.util.*;

class Solution {
    public int[] solution(String my_string) {

        my_string = my_string.replaceAll("[a-z]","");

        int[] answer = new int[my_string.length()];

        for(int i =0; i<my_string.length(); i++){
            answer[i] = my_string.charAt(i) - '0';
        }

        Arrays.sort(answer);

        return answer;
    }
}
```