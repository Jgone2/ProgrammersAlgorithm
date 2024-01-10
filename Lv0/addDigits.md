# 자릿수 더하기

## 📌 문제 설명

정수 n이 매개변수로 주어질 때 n의 각 자리 숫자의 합을 return하도록 solution 함수를 완성해주세요

### 제한 조건

- 0 ≤ n ≤ 1,000,000

### 입출력 예

| n      | result |
| ------ | ------ |
| 1234   | 10     |
| 930211 | 16     |

# 🧐 접근

n을 10씩 나누면서 연산

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        while (n >= 10) {
            int i = 0;
            i = n % 10;
            n /= 10;
            answer += i;
        }
        answer += n;
        return answer;
    }
}
```

# 💡 풀이

n이 10 이상일 때 n을 10씩 나누어서 일의 자리의 값을 추출.
그리고 n을 10으로 나눈 몫을 다시 n에 할당.
추출된 일의 자리 값을 answer에 더해줌.
마지막으로 남은 일의 자리 수를 반복문 밖에서 추가로 더한 값을 반환.

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        while(n>0){
            answer+=n%10;
            n/=10;
        }
        return answer;
    }
}
```
생각해보니 굳이 변수 i를 추가할 필요가 없고 0일때도 10으로 나누고 나머지값을 추출하면,
일의 자리 숫자가 추출되므로 굳이 불필요한 구분이었다는 생각이 든다.

# 📘 그 외의 풀이

###  =====================