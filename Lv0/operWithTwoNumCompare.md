# 두 수의 연산값 비교하기

## 📌 문제 설명

연산 ⊕는 두 정수에 대한 연산으로 두 정수를 붙여서 쓴 값을 반환합니다. 예를 들면 다음과 같습니다.

- 12 ⊕ 3 = 123
- 3 ⊕ 12 = 312
양의 정수 a와 b가 주어졌을 때, a ⊕ b와 2 * a * b 중 더 큰 값을 return하는 solution 함수를 완성해 주세요.

단, a ⊕ b와 2 * a * b가 같으면 a ⊕ b를 return 합니다.

### 제한 조건

- 1 ≤ a, b < 10,000

### 입출력 예

| a  | b  | result |
| -- | -- | ------ |
| 2  | 91 | 364    |
| 91 | 2  | 912    |

# 🧐 접근

삼항 연산자 사용

```java
class Solution {
    public int solution(int a, int b) {
        return Integer.parseInt("" + a + b) >= (2 * a * b) ? Integer.parseInt("" + a + b) : (2 * a * b);
    }
}
```

# 💡 풀이

삼항 연산자를 사용해서 비교연산을 수행했다.
다만 같은 연산이 두번씩 수행되므로, 연산값을 변수로 저장해서 연산하는게 더 효율적이긴 하다.



# 📘 그 외의 풀이

### log10

> 💡 10의 지수를 이용해 정수b의 승수를 구하고 1을 더해 자릿수를 알 수 있다. 여기에 10의 거듭제곱을 a에 곱해 정수 a와 b를 이어 붙일 수 있다. 생각지도 못한 방식이었다.

```java
class Solution {
    public int solution(int a, int b) {
        return Math.max(
            (int)Math.pow(10, (int)Math.log10(b) + 1) * a + b,
            2 * a * b
        );
    }
}
```