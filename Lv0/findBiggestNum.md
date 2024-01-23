# 가장 큰 수 찾기

## 📌 문제 설명

정수 배열 array가 매개변수로 주어질 때, 가장 큰 수와 그 수의 인덱스를 담은 배열을 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 1 ≤ array의 길이 ≤ 100
- 0 ≤ array 원소 ≤ 1,000
- array에 중복된 숫자는 없습니다.

### 입출력 예

| array          | result  |
| -------------- | ------- |
| [1, 8, 3]      | [8, 1]  |
| [9, 10, 11, 8] | [11, 2] |

# 🧐 접근

반복문을 수행하며 최댓값을 찾자

```java
class Solution {
    public int[] solution(int[] array) {
        int max = array[0];
        int idx = 0;
        for (int i = 0; i < array.length; i++) {
            if (array[i] > max) {
                max = array[i];
                idx = i;
            }
        }
        return new int[]{max, idx};
    }
}
```

# 💡 풀이

배열`array`의 첫번째 값을 최댓값으로 임의 지정하고, 반복문을 수행하며 큰 수가 나오면 max값을 교체하며 해당 값의 인덱스도 함께 저장한다.

# 📘 그 외의 풀이

### ==================