# 홀짝에 따라 다른 값 반환하기

## 📌 문제 설명

양의 정수 n이 매개변수로 주어질 때, n이 홀수라면 n 이하의 홀수인 모든 양의 정수의 합을 return 하고 n이 짝수라면 n 이하의 짝수인 모든 양의 정수의 제곱의 합을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ n ≤ 100

### 입출력 예

| n  | result |
| -- | ------ |
| 7  | 16     |
| 10 | 220    |

# 🧐 접근

조건에 맞춰 반복문 실행

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        if (n % 2 != 0) {
            for (int i = 1; i <= n; i += 2) {
                answer += i;
            }
        } else {
            for (int i = 2; i <= n; i += 2) {
                answer += Math.pow(i, 2);
            }
        }
        return answer;
    }
}
```

# 💡 풀이

홀수, 짝수 조건에 맞춰 n값에 대해 반복문을 수행하며 연산

# 📘 그 외의 풀이

###  1. Stream 사용

> 💡 Stream을 사용해서 연산

```java
import java.util.stream.IntStream;

class Solution {
    public int solution(int n) {
        if(n%2 == 0) {
            return IntStream.rangeClosed(1,n).filter(i->i%2==0).map(i->(int) Math.pow(i,2)).sum();
        }
        return IntStream.rangeClosed(1,n).filter(i->i%2==1).sum();
    }
}
```