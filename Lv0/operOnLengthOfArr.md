# 배열의 길이에 따라 다른 연산하기

## 📌 문제 설명

정수 배열 arr과 정수 n이 매개변수로 주어집니다. arr의 길이가 홀수라면 arr의 모든 짝수 인덱스 위치에 n을 더한 배열을, arr의 길이가 짝수라면 arr의 모든 홀수 인덱스 위치에 n을 더한 배열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ arr의 길이 ≤ 1,000
- 1 ≤ arr의 원소 ≤ 1,000
- 1 ≤ n ≤ 1,000

### 입출력 예

| arr                    | n | result                 |
| ---------------------- | - | ---------------------- |
| [49, 12, 100, 276, 33] | 2 | [76, 12, 127, 276, 60] |
| [444, 555, 666, 777]   | 2 | [444, 655, 666, 877]   |

# 🧐 접근

조건에 따라 연산수행

```java
class Solution {
    public int[] solution(int[] arr, int n) {
        if (arr.length % 2 == 0) {
            for (int i = 1; i < arr.length; i += 2) {
                arr[i] += n;
            }
        } else {
            for (int i = 0; i < arr.length; i += 2) {
            arr[i] += n;
            }
        }
        
        return arr;
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### 1. 삼항연산자 + for

> 💡 for문에서 idx값을 삼항연산자로 조건에 따라 초기화

```java
class Solution {
    public int[] solution(int[] arr, int n) {
        for(int idx=arr.length%2==0?1:0; idx<arr.length; idx+=2) {
            arr[idx]+=n;
        }

        return arr;
    }
}
```