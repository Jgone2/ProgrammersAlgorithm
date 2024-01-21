# 문자열 뒤의 n글자

## 📌 문제 설명

문자열 my_string과 정수 n이 매개변수로 주어질 때, my_string의 뒤의 n글자로 이루어진 문자열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- my_string은 숫자와 알파벳으로 이루어져 있습니다.
- 1 ≤ my_string의 길이 ≤ 1,000
- 1 ≤ n ≤ my_string의 길이

### 입출력 예

| my_string         | n  | result        |
| ----------------- | -- | ------------- |
| "ProgrammerS123"  | 11 | "grammerS123" |
| "He110W0r1d"      | 5  | "W0r1d"       |

# 🧐 접근

`substring()`메소드 사용

```java
class Solution {
    public String solution(String my_string, int n) {
        return my_string.substring(my_string.length() - n, my_string.length());
    }
}
```

# 💡 풀이

`substring(x, y)`메소드를 사용해서 문자열의 x인덱스부터 마지막까지 잘라낸 결과를 반환

> 💡 `substring()`메소드에서 y값은 지정하지 않으면 자동으로 문자열의 끝까지로 지정한다고 한다.

# 📘 그 외의 풀이

### ==================