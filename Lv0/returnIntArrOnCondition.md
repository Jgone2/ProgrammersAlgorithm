# 조건에 맞게 수열 변환하기 1

## 📌 문제 설명

정수 배열 arr가 주어집니다. arr의 각 원소에 대해 값이 50보다 크거나 같은 짝수라면 2로 나누고, 50보다 작은 홀수라면 2를 곱합니다. 그 결과인 정수 배열을 return 하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ arr의 길이 ≤ 1,000,000
- 1 ≤ arr의 원소의 값 ≤ 100

### 입출력 예

| arr                    | result                |
| ---------------------- | --------------------- |
| [1, 2, 3, 100, 99, 98] | [2, 2, 6, 50, 99, 49] |

# 🧐 접근

`stream()`을 사용해서 연산을 해보자.

```java
import java.util.Arrays;
class Solution {
    public int[] solution(int[] arr) {
        return Arrays.stream(arr)
            .map(num -> num >= 50 && num % 2 == 0 ? num / 2 
                      : num < 50 && num % 2 != 0 ? num * 2 : num)
            .toArray();
    }
}
```

# 💡 풀이

`map()`내에 삼항연산자를 사용해서 해당 조건에 맞는 값으로 연산을 수행하고 수행한 값들을 배열로 반환. 스트림을 사용하지 않고는 아래와 같이 풀이할 수 있다.

```java
class Solution {
    public int[] solution(int[] arr) {
        for(int i = 0; i < arr.length; i++) {
            if(arr[i] >= 50 && arr[i] % 2 == 0) {
                arr[i] /= 2;
            } else if(arr[i] < 50 && arr[i] % 2 != 0) {
                arr[i] *= 2;
            }
        }
        return arr;
    }
}
```

# 📘 그 외의 풀이

### ==================