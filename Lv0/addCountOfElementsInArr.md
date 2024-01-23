# 배열의 원소만큼 추가하기

## 📌 문제 설명

아무 원소도 들어있지 않은 빈 배열 X가 있습니다. 양의 정수 배열 arr가 매개변수로 주어질 때, arr의 앞에서부터 차례대로 원소를 보면서 원소가 a라면 X의 맨 뒤에 a를 a번 추가하는 일을 반복한 뒤의 배열 X를 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ arr의 길이 ≤ 100
- 1 ≤ arr의 원소 ≤ 100

### 입출력 예

| arr       | result                               |
| --------- | ------------------------------------ |
| [5, 1, 4] | [5, 5, 5, 5, 5, 1, 4, 4, 4, 4]       |
| [6, 6]    | [6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6] |
| [1]       | [1]                                  |

# 🧐 접근

이중 for문 사용

```java
class Solution {
    public int[] solution(int[] arr) {
        int size = 0;
        for (int e : arr) size += e;
        
        int[] answer = new int[size];
        int idx = 0;
        for (int e : arr) {
            for (int i = 0; i < e; i++) {
                answer[idx++] = e;
            }
        }
        return answer;
    }
}
```

# 💡 풀이

매개변수`arr`의 원소의 합을 구해 반환할 배열`answer`의 크기 지정을 해준다.
그 후 이중for문을 사용해 해당 원소의 수 만큼 해당 원소를 배열`answer`에 할당해준다.

# 📘 그 외의 풀이

### 1. repeat()

> 💡 repeat()메소드를 사용해서 원소의 개수만큼 반복 주입이 가능

```java
import java.util.stream.Stream;

class Solution {
    public int[] solution(int[] arr) {
        String answer = "";

        for(int i: arr) {
            answer += (String.valueOf(i)+",").repeat(i);
        }
        return Stream.of(answer.split(",")).mapToInt(Integer::parseInt).toArray(); 
    }
}
```