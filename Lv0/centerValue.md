# 중앙값 구하기

## 📌 문제 설명

중앙값은 어떤 주어진 값들을 크기의 순서대로 정렬했을 때 가장 중앙에 위치하는 값을 의미합니다. 예를 들어 1, 2, 7, 10, 11의 중앙값은 7입니다. 정수 배열 array가 매개변수로 주어질 때, 중앙값을 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- array의 길이는 홀수입니다.
- 0 < array의 길이 < 100
- -1,000 < array의 원소 < 1,000

### 입출력 예

| array             | result |
| ----------------- | ------ |
| [1, 2, 7, 10, 11] | 7      |
| [9, -1, 0]        | 0      |

# 🧐 접근

정렬 후 중앙값찾기

```java
import java.util.Arrays;
class Solution {
    public int solution(int[] array) {
        Arrays.sort(array);
        return array[array.length / 2];
    }
}
```

# 💡 풀이

중앙값을 구하기 위해 배열을 오름차순으로 정렬했고,
배열의 길이의 중간지점을 찾기위해 2로 나눴다.

# 📘 그 외의 풀이

###  1. 직접 정렬하기

> 💡 이중 for문을 사용해 직접 값들을 비교해가면서 정렬

```java
class Solution {
    public int solution(int[] array) {
        int answer = 0;

        for (int i = 0; i < array.length; i++) {
            for (int j = i; j < array.length; j++) {
                if (array[j] < array[i]) {
                    int temp = array[i];
                    array[i] = array[j];
                    array[j] = temp;
                }
            }
        }

        answer = array[array.length / 2];

        return answer;
    }
}
```