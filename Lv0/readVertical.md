# 세로 읽기

## 📌 문제 설명

문자열 my_string과 두 정수 m, c가 주어집니다. my_string을 한 줄에 m 글자씩 가로로 적었을 때 왼쪽부터 세로로 c번째 열에 적힌 글자들을 문자열로 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- my_string은 영소문자로 이루어져 있습니다.
- 1 ≤ m ≤ my_string의 길이 ≤ 1,000
- m은 my_string 길이의 약수로만 주어집니다.
- 1 ≤ c ≤ m

### 입출력 예

| my_string              | m   | c   | result        |
| ---------------------- | --- | --- | ------------- |
| "ihrhbakrfpndopljhygc" | 4   | 2   | "happy"       |
| "programmers"          | 1   | 1   | "programmers" |

# 🧐 접근

m과 c를 활용하여 연산을 줄이자

```java
class Solution {
    public String solution(String my_string, int m, int c) {
        StringBuilder sb = new StringBuilder();
        int idx = my_string.length();
        for(int i = c - 1; i < idx; i += m) {
            sb.append(my_string.charAt(i));
        }
        return sb.toString();
    }
}
```

# 💡 풀이

문자열에서 인덱스 `c-1`의 값이 첫 값이고 m글자씩 가로로 한줄을 만들었을때 시작점이 `c-1`일 때 인덱스 `m`씩 더하면 항상 c번째 열에 도달

# 📘 그 외의 풀이

### ===================
