# 약수의 합

## 📌 문제 설명

정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 완성해주세요.

### 제한 조건

- n은 0 이상 3000이하인 정수입니다.

### 입출력 예

| n | return |
| --- | ------ |
| 12  | 28     |
| 5   | 6      |

# 🧐 접근

for문으로 0부터 11까지의 수 중에 나눠서 0이 되는 숫자를 찾고 나머지가 0인 값에 1을 더함.

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        int num = n;
        for(int i = 0; i < num; i++) {
            if(n % (i + 1) == 0) {
                answer += (i + 1);
            }
            continue;
        }
        return answer;
    }

    public static void main(String[] args) {
        int num1 = 12;
        int num2 = 5;

        Solution result = new Solution();

        System.out.println("12의 약수의 합: " + result.solution(12));
        System.out.println("6의 약수의 합: " + result.solution(6));
    }
}
```

# 💡 풀이

for문으로 0부터 11까지의 숫자를 순회하며 n값에 (i + 1)을 한 값으로 나눠서 나머지가 0인 값에 +1을 헌 휴 answer에 더합니다.  
조건문에 해당하지 않는 값들은 값을 저장하지 않고 continue를 사용하여 다음 반복으로 넘어갑니다.
그러면 answer에는 나머지가 0이됐던 약수들의 합이 구해집니다.

# 📘 그 외의 풀이

### 1. 반복문의 조건식에서 i값을 1부터 num까지 설정

#### 반복문의 조건식에서 i값을 1부터 num까지 설정

> 💡 반복문의 조건문에서 int i 를 1로 초기화 하고 i <= num으로 설정하면 위의 풀이에서 반복됐던 if문의 조건식과 if문 내의 코드에서 (i + 1)이라는 중복 코드를 줄일 수 있다.

```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        int num = n;
        for(int i = 1; i <= num; i++) {
            if(n % i == 0) {
                answer += i;
            }
            continue;
        }
        return answer;
    }

    public static void main(String[] args) {
        int num1 = 12;
        int num2 = 5;

        Solution result = new Solution();

        System.out.println("12의 약수의 합: " + result.solution(12));
        System.out.println("6의 약수의 합: " + result.solution(6));
    }
}
```
