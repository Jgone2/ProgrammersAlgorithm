# 문자열의 앞의 n글자

## 📌 문제 설명

문자열 my_string과 정수 n이 매개변수로 주어질 때, my_string의 앞의 n글자로 이루어진 문자열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- my_string은 숫자와 알파벳으로 이루어져 있습니다.
- 1 ≤ my_string의 길이 ≤ 1,000
- 1 ≤ n ≤ my_string의 길이

### 입출력 예
| my_string        | n  | result        |
| ---------------- | -- | ------------- |
| "ProgrammerS123" | 11 | "ProgrammerS" |
| "He110W0r1d"     | 5  | "He110"       |

# 🧐 접근

substring을 사용해서 새로운 문자열을 생성하자

```java
class Solution {
    public String solution(String my_string, int n) {
        return my_string.substring(0, n);
    }
}
```

# 💡 풀이

String 클래스 메소드인 `substring()`을 사용해서 0번째부터 n-1번째 문자열까지 추출.

# 📘 그 외의 풀이

###  ================