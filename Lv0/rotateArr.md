# 배열 회전시키기

## 📌 문제 설명

정수가 담긴 배열 numbers와 문자열 direction가 매개변수로 주어집니다. 배열 numbers의 원소를 direction방향으로 한 칸씩 회전시킨 배열을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 3 ≤ numbers의 길이 ≤ 20
- direction은 "left" 와 "right" 둘 중 하나입니다.

### 입출력 예

| numbers                   | direction | result                    |
| ------------------------- | --------- | ------------------------- |
| [1, 2, 3]                 | "right"   | [3, 1, 2]                 |
| [4, 455, 6, 4, -1, 45, 6] | "left"    | [455, 6, 4, -1, 45, 6, 4] |

# 🧐 접근

조건문을 사용해 각 조건에 부합하는 연산식 수행

```java
class Solution {
    public int[] solution(int[] numbers, String direction) {
        int[] answer = {};
        if (direction.equals("right")) {
            int last = numbers[numbers.length - 1];
            System.arraycopy(numbers, 0, numbers, 1, numbers.length - 2);
            numbers[0] = last;
        } else {
            int first = numbers[0];
            System.arraycopy(numbers, 1, numbers, 0, numbers.length - 1);
            numbers[numbers.length - 1] = first;
        }
        return numbers;
    }
}
```

# 💡 풀이

direction이 `right`일 때 numbers의 마지막 원소를 변수`last`에 할당하고 배열 복사를 통해서 배열`numbers`의 0번째 인덱스부터 마지막 인덱스를 제외한 모든 원소를 배열`numbers`의 1번 인덱스부터 채워넣도록 하고, 0번 인덱스에 기존 마지막 원소 값이었던 last를 할당한다.

direction이 `left`일때는 number의 첫 번째 원소를 변수`first`에 할당하고 배열 복사를 통해서 배열`numbers`의 1번 인덱스부터 마지막 인덱스의 원소까지 배열`numbers`의 0번 인덱스부터 채워넣고, 마지막 인덱스에 기존의 첫번째 원소 값이었던 first를 할당.
# 📘 그 외의 풀이

### ==============