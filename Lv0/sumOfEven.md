# 짝수의 합

## 📌 문제 설명

정수 n이 주어질 때, n이하의 짝수를 모두 더한 값을 return 하도록 solution 함수를 작성해주세요.

### 제한 조건

- 0 < n ≤ 1000

### 입출력 예

| n   | result |
| --- | ------ |
| 10  | 30     |
| 4   | 6      |

# 🧐 접근

제한 조건의 범위를 만족할 시 해당 범위의 짝수를 모두 연산

```java
class Solution {
    public int solution(int n) {
        if(0 < n && n <= 1_000) {
            return IntStream.rangeClosed(0, n)
                .filter(e -> e % 2 == 0)
                .sum();
        }
        return -1;
    }
}
```

# 💡 풀이

제한 조건에 부합한 값을 얻기 위해 if문을 통해 범위를 지정해주고, stream을 통해 범위 내의 짝수를 모두 더해줌.

> 💡 **추가적으로 알게 된 점**<br />
> IntStream.rangeClosed()는 두 번째 매개변수의 값도 포함한다.<br />
> IntStream.range()는 두 번째 매개변수의 값은 포함하지 않는다.

# 📘 그 외의 풀이

### 1. for문 사용

> 💡 반복문에서 초기 값i를 2로 설정한 후 i 값을 2씩 더해주며 순회하면 불필요한 순회를 줄일 수 있다.

```java
class Solution {
    public int solution(int n) {
        int answer = 0;

        for(int i=2; i<=n; i+=2){
            answer+=i;
        }

        return answer;
    }
}
```
