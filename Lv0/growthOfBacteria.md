# 세균 증식

## 📌 문제 설명

어떤 세균은 1시간에 두배만큼 증식한다고 합니다. 처음 세균의 마리수 n과 경과한 시간 t가 매개변수로 주어질 때 t시간 후 세균의 수를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ n ≤ 10
- 1 ≤ t ≤ 15

### 입출력 예
| n | t  | result  |
| - | -- | ------- |
| 2 | 10 | 2048    |
| 7 | 15 | 229,376 |

# 🧐 접근

제곱근으로 풀이하자

```java
class Solution {
    public int solution(int n, int t) {
        return n * (int)Math.pow(2, t);
    }
}
```

# 💡 풀이

1시간마다 2배 증식 -> 2의 제곱값 생성
2의 제곱값과 n을 곱함

# 📘 그 외의 풀이

###  1. 비트연산

> 💡 비트연산으로 왼쪽으로 시프트를 하면 시프트 한번당 2를 곱한 값과 동일. 시간만큼 제곱가능.

```java
class Solution {
    public int solution(int n, int t) {
        int answer = 0;

        answer = n << t;

        return answer;
    }
}
```