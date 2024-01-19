# 원소들의 곱과 합

## 📌 문제 설명

정수가 담긴 리스트 num_list가 주어질 때, 모든 원소들의 곱이 모든 원소들의 합의 제곱보다 작으면 1을 크면 0을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 2 ≤ num_list의 길이 ≤ 10
- 1 ≤ num_list의 원소 ≤ 9

### 입출력 예

| num_list        | result |
| --------------- | ------ |
| [3, 4, 5, 2, 1] | 1      |
| [5, 7, 8, 3]    | 0      |

# 🧐 접근

삼항연산자 사용

```java
class Solution {
    public int solution(int[] num_list) {
        int multiple = 1;
        int sum = 0;
        for(int num : num_list) {
            multiple *= num;
            sum += num;
        }
        return multiple < Math.pow(sum, 2) ? 1 : 0 ;
    }
}
```

# 💡 풀이

배열 원소의 합과 곱을 따로 구해준 다음,
삼항 연산자를 통해 조건에 부합하는 값을 반환

# 📘 그 외의 풀이

### 1. Stream() 사용

> 💡 `reduce()`메소드는 처음 봤는데 스트림의 원소들을 연산 수행해서 하나의 결과로 출력해준다고 한다.

```java
import java.util.Arrays;

class Solution {
    public int solution(int[] numList) {
        return (Arrays.stream(numList).reduce((acc, i) -> acc * i).getAsInt() < Math.pow(Arrays.stream(numList).sum(), 2)) ? 1 : 0;
    }
}
```