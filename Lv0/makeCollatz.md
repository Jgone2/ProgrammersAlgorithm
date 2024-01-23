# 콜라츠 수열 만들기

## 📌 문제 설명

모든 자연수 x에 대해서 현재 값이 x이면 x가 짝수일 때는 2로 나누고, x가 홀수일 때는 3 * x + 1로 바꾸는 계산을 계속해서 반복하면 언젠가는 반드시 x가 1이 되는지 묻는 문제를 콜라츠 문제라고 부릅니다.

그리고 위 과정에서 거쳐간 모든 수를 기록한 수열을 콜라츠 수열이라고 부릅니다.

계산 결과 1,000 보다 작거나 같은 수에 대해서는 전부 언젠가 1에 도달한다는 것이 알려져 있습니다.

임의의 1,000 보다 작거나 같은 양의 정수 n이 주어질 때 초기값이 n인 콜라츠 수열을 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ n ≤ 1,000

### 입출력 예

| n  | result                  |
| -- | ----------------------- |
| 10 | [10, 5, 16, 8, 4, 2, 1] |

# 🧐 접근

`while`문 수행

```java
import java.util.ArrayList;
import java.util.List;
class Solution {
    public int[] solution(int n) {
        int[] answer = {};
        List<Integer> arrList = new ArrayList<>();
        while(n != 1) {
            arrList.add(n);
            if (n % 2 == 0) {    
                n /= 2;
            } else {
                n = 3 * n + 1;
            }
        }
        arrList.add(n);
        answer = new int[arrList.size()];
        for (int i = 0; i < answer.length; i++) {
            answer[i] = arrList.get(i);
        }
        return answer;
    }
}
```

# 💡 풀이

콜라츠 수열의 크기를 미리 알 수 없으므로 ArrayList를 생성해주고 `while`문을 수행하면서 n이 1이 아니라면 반복수행하도록 한다.
연산된 값을 `arrList`에 추가해주고 조건에 맞게 n을 연산해준다.
n이 1이됐을 때 반복문을 빠져나와 추가해주고 배열 answer에 해당 값들을 추가해 준다음 반환

# 📘 그 외의 풀이

### ==================