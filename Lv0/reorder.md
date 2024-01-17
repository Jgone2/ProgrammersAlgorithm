# 순서 바꾸기

## 📌 문제 설명

정수 리스트 num_list와 정수 n이 주어질 때, num_list를 n 번째 원소 이후의 원소들과 n 번째까지의 원소들로 나눠 n 번째 원소 이후의 원소들을 n 번째까지의 원소들 앞에 붙인 리스트를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 2 ≤ num_list의 길이 ≤ 30
- 1 ≤ num_list의 원소 ≤ 9
- 1 ≤ n ≤ num_list의 길이

### 입출력 예

| num_list	      | n |	result          |
| --------------- | - | --------------- |
| [2, 1, 6]       |	1 |	[1, 6, 2]       |
| [5, 2, 1, 7, 5] |	3 | [7, 5, 5, 2, 1] |

# 🧐 접근

반복문을 통해서 재배열

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int[] answer = new int[num_list.length];
        for (int i = 0; i < num_list.length; i++) {
            answer[(i - n + num_list.length) % num_list.length] = num_list[i];
        }
        return answer;
    }
}
```

# 💡 풀이

먼저 순서를 바꾼 배열을 담을 배열`answer`의 길이를 배열`num_list`와 맞춰준다.
반복문을 통해 원소 재배치를 한다.
배열`[2, 1, 6]`을 예시로 했을 때
`answer[(0 - 1 + 3) % 3] = num_list[i]` 를 수행하면 `answer[2]`에 `num_list`의 0번째 인덱스에 속해있던 `2`가 할당되게 된다. 마찬가지로 반복해서
새롭게 할당해주면 순서교환을 할 수 있다.

# 📘 그 외의 풀이

### 1. 반복문 나눠서 실행

> 💡 사실 가장 먼저 생각난 방법이다..시간, 공간 복잡도 그리고 메모리 효율성측에서 생각해봐도 내가 푼 코드랑 차이가 없지만 그냥 한번만 쓰고싶었다..

```java
class Solution {
    public int[] solution(int[] num_list, int n) {
        int idx = 0;
        int[] answer = new int[num_list.length];
        for (int i = n;i < num_list.length;i++)
            answer[idx++] = num_list[i];
        for (int i = 0;i < n;i++)
            answer[idx++] = num_list[i];
        return answer;
    }
}
```