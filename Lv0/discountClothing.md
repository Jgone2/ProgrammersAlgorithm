# 옷가게 할인 받기

## 📌 문제 설명

머쓱이네 옷가게는 10만 원 이상 사면 5%, 30만 원 이상 사면 10%, 50만 원 이상 사면 20%를 할인해줍니다.
구매한 옷의 가격 price가 주어질 때, 지불해야 할 금액을 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 10 ≤ price ≤ 1,000,000
  - price는 10원 단위로(1의 자리가 0) 주어집니다.
- 소수점 이하를 버린 정수를 return합니다.

### 입출력 예

| price   | result  |
| ------- | ------- | 
| 150,000 | 142,500 |
| 580,000 | 464,000 |

# 🧐 접근

Java 17에서 새롭게 도입된 형태의 switch문을 사용해보자

```java
class Solution {
    public int solution(int price) {
        return switch ((price >= 500_000) ? 3 
                      : (price >= 300_000) ? 2 
                      : (price >= 100_000) ? 1 : 0) {
            case 3 -> (int)(price * 0.8);
            case 2 -> (int)(price * 0.9);
            case 1 -> (int)(price * 0.95);
            default -> price;
        };
    }
}
```

# 💡 풀이

switch문을 사용해서 각 조건에 맞는 할인율로 연산

# 📘 그 외의 풀이

###  ================