# 카운트 다운

## 📌 문제 설명

정수 start_num와 end_num가 주어질 때, start_num에서 end_num까지 1씩 감소하는 수들을 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 0 ≤ end_num ≤ start_num ≤ 50

### 입출력 예

| start | end_num | result                    |
| ----- | ------- | ------------------------- |
| 10    | 3       | [10, 9, 8, 7, 6, 5, 4, 3] |

# 🧐 접근

반복문 통해 연산

```java
class Solution {
    public int[] solution(int start, int end_num) {
        int[] answer = new int[start - end_num + 1];
        int index = 0;
        for(int i = start; i >= end_num; i--) {
            answer[index++] += i;
        }
        return answer;
    }
}
```

# 💡 풀이

start값에 end_num을 뺀다음 1을 더한값만큼 배열answer의 크기로 지정
반복문을 통해서 start값부터 end_num값을 포함해 1씩 뺴면서 배열answer에 값 할당

# 📘 그 외의 풀이

### ==================