# n개 간격의 원소들

## 📌 문제 설명

정수 리스트 num_list와 정수 n이 주어질 때, num_list의 첫 번째 원소부터 마지막 원소까지 n개 간격으로 저장되어있는 원소들을 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 5 ≤ num_list의 길이 ≤ 20
- 1 ≤ num_list의 원소 ≤ 9
- 1 ≤ n ≤ 4

### 입출력 예

| array              | n | result    |
| ------------------ | - | --------- |
| [4, 2, 6, 1, 7, 6] | 2 | [4, 6, 7] |
| [4, 2, 6, 1, 7, 6] | 4 | [4, 7]    |

# 🧐 접근

올림 연산을 사용해서 배열의 크기를 지정 후 연산

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = {};
        int arrLength = (int)Math.ceil((double) num_list.length / n);
        answer = new int[arrLength];
        int index = 0;
        for (int i = 0; i < num_list.length; i += n) {          
            answer[index] = num_list[i];
            ++index;
        }
        return answer;
    }
}
```

# 💡 풀이

올림 연산 `ceil`을 사용해서 배열의 크기를 지정한 후,
반복문을 통해 배열의 첫번째 인덱스부터 n개 간격의 index에 저장되어있는 원소들을 배열answer에 저장

# 📘 그 외의 풀이

###  =====================