# 더 크게 합치기

## 📌 문제 설명

연산 ⊕는 두 정수에 대한 연산으로 두 정수를 붙여서 쓴 값을 반환합니다. 예를 들면 다음과 같습니다.

- 12 ⊕ 3 = 123
- 3 ⊕ 12 = 312
  
양의 정수 a와 b가 주어졌을 때, a ⊕ b와 b ⊕ a 중 더 큰 값을 return 하는 solution 함수를 완성해 주세요.

단, a ⊕ b와 b ⊕ a가 같다면 a ⊕ b를 return 합니다.

### 제한 조건

- 1 ≤ a, b < 10,000

### 입출력 예

| a  | b  | result |
| -- | -- | ------ |
| 9  | 91 | 991    |
| 89 | 8  | 898    |

# 🧐 접근

`StringBuilder`사용

```java
class Solution {
    public int solution(int a, int b) {
        StringBuilder typeA = new StringBuilder(String.valueOf(a)).append(b);
        StringBuilder typeB = new StringBuilder(String.valueOf(b)).append(a);
        
        return Math.max(Integer.parseInt(typeA.toString()), Integer.parseInt(typeB.toString()));
    }
}
```

# 💡 풀이

`StringBuilder`를 사용해서 정수를 이어붙인 후, `Math.max()`메소드를 사용하여 최댓값을 반환한다.
아래와 같이 `""`를 사용해도 무관하다.

```java
class Solution {
    public int solution(int a, int b) {
        return Math.max(Integer.parseInt("" + a + b), Integer.parseInt(""+ b + a));
    }
}
```

# 📘 그 외의 풀이

### ==================