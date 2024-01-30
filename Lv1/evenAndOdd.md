# 짝수와 홀수

## 📌 문제 설명

정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수, solution을 완성해주세요.

### 제한 조건

- num은 int 범위의 정수입니다.
- 0은 짝수입니다.

### 입출력 예
| num | return |
| --- | ------ |
| 3   | "Odd"  |
| 4   | "Even" |


# 🧐 접근

삼항 연산자를 사용해 짝수와 홀수인 경우를 각각 나눠서 결과값 return하기.

```java
public class Solution {
    public String solution(int num) {
        return num % 2 == 0 ? "Even": "Odd";
    }
}

```

# 💡 풀이

삼항 연산자를 사용해서 해당 나머지 연산의 결과값이 0이라면 `Even`아니라면 `Odd`를 반환


# 📘 그 외의 풀이

### =============