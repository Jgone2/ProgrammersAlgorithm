# 아이스 아메리카노

## 📌 문제 설명

머쓱이는 추운 날에도 아이스 아메리카노만 마십니다. 아이스 아메리카노는 한잔에 5,500원입니다. 머쓱이가 가지고 있는 돈 money가 매개변수로 주어질 때, 머쓱이가 최대로 마실 수 있는 아메리카노의 잔 수와 남는 돈을 순서대로 담은 배열을 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 0 < money ≤ 1,000,000

### 입출력 예

| money  | result    |
| ------ | --------- |
| 5,500  | [1, 0]    |
| 15,000 | [2, 4000] |

# 🧐 접근

최대 잔 수와 잔돈을 각자 개산해서 배열에 삽입

```java
class Solution {
    public int[] solution(int money) {
        final int AMERICANO = 5_500;
        int maxCups = money / AMERICANO;
        int leftMoney = money % AMERICANO;
        return new int[]{maxCups, leftMoney};
    }
}
```

# 💡 풀이

나누기 연산자와 나머지 연산자를 사용해서 최대 잔 수와 잔돈을 연산한 후 배열로 생성해서 반환

# 📘 그 외의 풀이

###  =====================