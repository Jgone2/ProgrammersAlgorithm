# 마지막 두 원소

## 📌 문제 설명

정수 리스트 num_list가 주어질 때, 마지막 원소가 그전 원소보다 크면 마지막 원소에서 그전 원소를 뺀 값을 마지막 원소가 그전 원소보다 크지 않다면 마지막 원소를 두 배한 값을 추가하여 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 2 ≤ num_list의 길이 ≤ 10
- 1 ≤ num_list의 원소 ≤ 9

### 입출력 예
| num_list        | result              |
| --------------- | ------------------- |
| [2, 1, 6]       | [2, 1, 6, 5]        |
| [5, 2, 1, 7, 5] | [5, 2, 1, 7, 5, 10] |

# 🧐 접근

배열을 복사해서 연산하자

```java
import java.lang.System;

class Solution {
    public int[] solution(int[] num_list) {
        int[] arr = new int[num_list.length + 1];
        System.arraycopy(num_list, 0, arr, 0, num_list.length);
        if(num_list[num_list.length - 1] > num_list[num_list.length - 2]) {
            arr[num_list.length] = num_list[num_list.length - 1] - num_list[num_list.length- 2];
        } else {
            arr[num_list.length] = num_list[num_list.length - 1] * 2;
        }
        return arr;
    }
}
```

# 💡 풀이

기존 배열보다 길이가 1 더 긴 배열을 생성해서 기존 배열을 복사.
복사된 배열에 연산 수행한 결과를 추가

# 📘 그 외의 풀이

###  1. stream 사용

> 💡 iterate로 1씩 증가하는 무한스트림을 생성 후 스트림의 길이를 배열`num_list`
의 길이 + 1만큼 제한을 지정.
> 이후 조건에 맞는 결과값 추출

```java
class Solution {
    public int[] solution(int[] num_list) {
        return IntStream.iterate(0, i -> i + 1)
                        .limit(num_list.length + 1)
                        .map(i -> i == num_list.length ? (num_list[i - 1] > num_list[i - 2] ? num_list[i - 1] - num_list[i - 2] : 2 * num_list[i - 1]) : num_list[i])
                        .toArray();
    }
}
```