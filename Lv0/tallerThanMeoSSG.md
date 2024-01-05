# 머쓱이보다 키 큰 사람

## 📌 문제 설명

머쓱이는 학교에서 키 순으로 줄을 설 때 몇 번째로 서야 하는지 궁금해졌습니다. 머쓱이네 반 친구들의 키가 담긴 정수 배열 array와 머쓱이의 키 height가 매개변수로 주어질 때, 머쓱이보다 키 큰 사람 수를 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 1 ≤ array의 길이 ≤ 100
- 1 ≤ height ≤ 200
- 1 ≤ array의 원소 ≤ 200


### 입출력 예
| array                | height | result |
| -------------------- | ------ | ------ |
| [149, 180, 192, 170] | 167    | 3      |
| [180, 120, 140]      | 190    | 0      |

# 🧐 접근

배열에서 값을 추출하고 카운팅하자

```java
import java.util.Arrays;
class Solution {
    public int solution(int[] array, int height) {
        return (int)Arrays.stream(array)
            .filter(e -> e > height)
            .count();
    }
}
```

# 💡 풀이

filter를 사용해서 배열 내에 조건에 부합하는 값을 추출하고 카운팅.

# 📘 그 외의 풀이

###  =============