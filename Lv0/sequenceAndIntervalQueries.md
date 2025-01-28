# 수열과 구간 쿼리 1

## 📌 문제 설명

정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [s, e] 꼴입니다.

각 query마다 순서대로 s ≤ i ≤ e인 모든 i에 대해 arr[i]에 1을 더합니다.

위 규칙에 따라 queries를 처리한 이후의 arr를 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ arr의 길이 ≤ 1,000
  - 0 ≤ arr의 원소 ≤ 1,000,000
- 1 ≤ queries의 길이 ≤ 1,000
  - 0 ≤ s ≤ e < arr의 길이

### 입출력 예

| arr             | queries                  | result          |
| --------------- | ------------------------ | --------------- |
| [0, 1, 2, 3, 4] | [[0, 1], [1, 2], [2, 3]] | [1, 3, 4, 4, 4] |

# 🧐 접근

중첩 반복문을 순회하자

```java
class Solution {
    public int[] solution(int[] arr, int[][] queries) {
        for (int[] query : queries) {
            int s = query[0];
            int e = query[1];
            for (int i = s; i <= e; i++) {
                arr[i] += 1;
            }
        }
        return arr;
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### =====================
