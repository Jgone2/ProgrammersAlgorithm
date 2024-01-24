# 홀수 vs 짝수

## 📌 문제 설명

정수 리스트 num_list가 주어집니다. 가장 첫 번째 원소를 1번 원소라고 할 때, 홀수 번째 원소들의 합과 짝수 번째 원소들의 합 중 큰 값을 return 하도록 solution 함수를 완성해주세요. 두 값이 같을 경우 그 값을 return합니다.

### 제한 조건

- 5 ≤ num_list의 길이 ≤ 50
- -9 ≤ num_list의 원소 ≤ 9

### 입출력 예

| num_list           | result |
| ------------------ | ------ |
| [4, 2, 6, 1, 7, 6] | 17     |
| [-1, 2, 5, 6, 3]   | 8      |

# 🧐 접근

반복문 수행

```java
class Solution {
    public int solution(int[] num_list) {
        int sumEven = 0;
        int sumOdd = 0;
        for (int i = 0; i < num_list.length; i += 2) sumOdd += num_list[i];
        for (int i = 1; i < num_list.length; i += 2) sumEven += num_list[i];
        return sumOdd > sumEven ? sumOdd : sumEven;
    }
}
```

# 💡 풀이

반복문 수행해서 합을 구하고 두 수를 비교해 큰 값을 반환

# 📘 그 외의 풀이

### ==================