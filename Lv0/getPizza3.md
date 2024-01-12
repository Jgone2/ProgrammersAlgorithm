# 피자 나눠 먹기 (3)

## 📌 문제 설명

머쓱이네 피자가게는 피자를 두 조각에서 열 조각까지 원하는 조각 수로 잘라줍니다. 피자 조각 수 slice와 피자를 먹는 사람의 수 n이 매개변수로 주어질 때, n명의 사람이 최소 한 조각 이상 피자를 먹으려면 최소 몇 판의 피자를 시켜야 하는지를 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 2 ≤ slice ≤ 10
- 1 ≤ n ≤ 100

### 입출력 예

| slice | n  | result |
| ----- | -- | ------ |
| 7     | 10 | 2      |
| 4     | 12 | 3      |

# 🧐 접근

올림 메서드인 `ceil`을 사용하자

```java
import java.lang.*;
class Solution {
    public int solution(int slice, int n) {
        return (int) Math.ceil((double)n / slice);
    }
}
```

# 💡 풀이

올림 메서드인 `ceil()`을 이용한다. 매개변수로 사람수(n)을 피자 조각 수(slice)로 나누면 각 사람이 최소 한 조각 이상 먹기 위해 필요한 피자 판 수를 계산할 수 있다.
여기서 

```java
class Solution {
    public int solution(String my_string) {
        int answer = 0;
        for (char c : my_string.toCharArray()) {
            if (Character.isDigit(c)) answer += Character.getNumericValue(c);
        }
        return answer;
    }
}
```

위의 코드는 문자열my_string을 char형 배열로 변환 후 루프문을 통해 한 글자씩
`isDigit`메서드를 사용해 해당 문자가 숫자(0-9)인지 확인한다. 

조건에 부합할경우 `getNumericValue`를 사용해서 정수형으로 변환해 answer에 더해준다.

# 📘 그 외의 풀이

### ==================