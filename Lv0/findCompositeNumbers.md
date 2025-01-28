# 합성수 찾기

## 📌 문제 설명

약수의 개수가 세 개 이상인 수를 합성수라고 합니다. 자연수 n이 매개변수로 주어질 때 n이하의 합성수의 개수를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ n ≤ 100

### 입출력 예

| n   | result |
| --- | ------ |
| 10  | 5      |
| 15  | 8      |

# 🧐 접근

중첩반복문을 사용하여 n이하의 정수를 순회하면 해당 수에서 반복문을 순회하여 약수의 개수를 count

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        int count = 0;
        for(int i = 4; i <= n; i++) {
            for(int j = 1; j <= i; j++) {
                if(i % j == 0) count++;
            }
            if(count > 2) answer++;
            count = 0;
        }
        return answer;
    }
}
```

# 💡 풀이

3이하의 수는 약수의 개수가 3개가 아니므로 외부 순회에서는 정수 4부터 순회를 시작한다.

# 📘 그 외의 풀이

### 1. Stream사용

> 💡 rangeClosed를 사용하여 주어진 정수 이하의 수를 찾아 연산 후 조건 만족 시 count

```java
import java.util.stream.IntStream;

class Solution {
    public int solution(int n) {
        return (int) IntStream.rangeClosed(1, n).filter(i -> (int) IntStream.rangeClosed(1, i).filter(i2 -> i % i2 == 0).count() > 2).count();
    }
}
```

### 2. 4이상의 짝수는 모두 합성수

> 💡 4이상의 짝수는 모두 합성수인 점을 활용해 반복문 순회횟수를 줄일 수 있음

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        for(int i=4; i<n+1; i++){
            if(i%2==0) {
                answer++; // 4이상 짝수는 전부 합성수
                continue;
            }
            else{
                for(int k=3; k<i/2; k=k+2){
                    if(i%k==0){
                        answer++;
                        break;
                    }
                }
            }
        }
        return answer;
    }
}
```
