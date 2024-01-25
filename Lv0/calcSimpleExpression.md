# 간단한 식 계산하기

## 📌 문제 설명

문자열 binomial이 매개변수로 주어집니다. binomial은 "a op b" 형태의 이항식이고 a와 b는 음이 아닌 정수, op는 '+', '-', '*' 중 하나입니다. 주어진 식을 계산한 정수를 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 0 ≤ a, b ≤ 40,000
- 0을 제외하고 a, b는 0으로 시작하지 않습니다.

### 입출력 예

| binomial        | result     |
| --------------- | ---------- |
| "43 + 12"       | 55         |
| "0 - 7777"      | -7777      |
| "40000 * 40000" | 1600000000 |

# 🧐 접근

`switch`문 사용

```java
class Solution {
    public int solution(String binomial) {
        String[] split = binomial.split(" ");
        int a = Integer.parseInt(split[0]);
        int b = Integer.parseInt(split[2]);
        switch (split[1].charAt(0)) {
            case '+': return a + b;
            case '-': return a - b;
            case '*': return a * b;
        }
        return 0;
    }
}
```

# 💡 풀이

공백을 기준으로 문자열을 나눠서 배열`split`에 값을 할당하고
인덱스 0번과 2번은 정수형으로 변환해 저장하고 switch문에서 1번인덱스의 값을 기준으로 case를 만들어서 연산

# 📘 그 외의 풀이

### ==========