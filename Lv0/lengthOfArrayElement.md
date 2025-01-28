# 배열 원소의 길이

## 📌 문제 설명

문자열 배열 strlist가 매개변수로 주어집니다. strlist 각 원소의 길이를 담은 배열을 retrun하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ strlist 원소의 길이 ≤ 100
- strlist는 알파벳 소문자, 대문자, 특수문자로 구성되어 있습니다.

### 입출력 예

| strlist                        | result       |
| ------------------------------ | ------------ |
| ["We", "are", "the", "world!"] | [2, 3, 3, 6] |
| ["I", "Love", "Programmers."]  | [1, 4, 12]   |

# 🧐 접근

반복문을 통해서 배열내의 원소값들의 원소를 answer에 삽입

````java

```java
class Solution {
    public int[] solution(String[] strlist) {
        int[] answer = new int[strlist.length];
        int i = 0;
        for(String str : strlist) {
            answer[i] = str.length();
            i++;
        }
        return answer;
    }
}
````

# 💡 풀이

먼저 answer배열의 길이 지정을 통해 초기화해주고, iter문으로 각 원소를 추출해 원소의 길이를 answer배열에 삽입.

# 📘 그 외의 풀이

### 1. Stream

> 💡 Stream을 활용한 풀이

```java
import java.util.Arrays;

class Solution {
    public int[] solution(String[] strList) {
        return Arrays.stream(strList).mapToInt(String::length).toArray();
    }
}
```
