# 날짜 비교하기

## 📌 문제 설명

정수 배열 date1과 date2가 주어집니다. 두 배열은 각각 날짜를 나타내며 [year, month, day] 꼴로 주어집니다. 각 배열에서 year는 연도를, month는 월을, day는 날짜를 나타냅니다.

만약 date1이 date2보다 앞서는 날짜라면 1을, 아니면 0을 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- date1의 길이 = date2의 길이 = 3
  - 0 ≤ year ≤ 10,000
  - 1 ≤ month ≤ 12
  - day는 month에 따라 가능한 날짜로 주어집니다.

### 입출력 예

| date1          | date2          | result |
| -------------- | -------------- | ------ |
| [2021, 12, 28] | [2021, 12, 29] | 1      |
| [1024, 10, 24] | [1024, 10, 24] | 0      |

# 🧐 접근

LocalDate의 메서드를 활용하자

```java
import java.time.LocalDate;

class Solution {
    public int solution(int[] date1, int[] date2) {
        LocalDate ld1 = LocalDate.of(date1[0], date1[1], date1[2]);
        LocalDate ld2 = LocalDate.of(date2[0], date2[1], date2[2]);

        return ld1.compareTo(ld2) < 0 ? 1 : 0;
    }
}
```

# 💡 풀이

LocalDate를 사용하여 날짜형식을 맞추고 `compareTo()`메서드를 사용해 비교 후 return

# 📘 그 외의 풀이

### 1. Arrays.compare() 사용

> 💡 Arrays의 compare() 메서드를 사용하여 비교

```java
import java.util.*;

class Solution {
    public int solution(int[] date1, int[] date2) {
        return Arrays.compare(date1, date2) < 0 ? 1 : 0;
    }
}
```
