# 짝수와 홀수

## 📌 문제 설명
정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수, solution을 완성해주세요.

### 제한 조건
num은 int 범위의 정수입니다.
0은 짝수입니다.

### 입출력 예
num | return
--|--
3 | "Odd"
4 | "Even"


# 🧐 접근
'조건문'을 사용해 짝수와 홀수인 경우를 각각 나눠서 결과값 return하기.

```java
class Solution {
    public String solution(int num) {
        String answer = "";

        if(num % 2 == 0) {
            answer = "Even";
        } else {
            answer = "Odd";
        }
        return answer;
    }
    
    public static void main(String[] args) {
        
        Solution result = new Solution();
        
        // result값 출력
        System.out.println("결과 : " + result.solution(3));
        System.out.println("결과 : " + result.solution(4));
    }
}
```

# 💡 풀이
짝수와 홀수여부 판단을 위해 `%`연산자를 사용 합니다.
`%`연산자는 나머지 연산자입니다.
파라미터 값으로 주어진 num을 2로 나누었을 때 나머지가 0이라면 짝수이기 때문에 "Even"을 return하고 그 외의 경우(나머지가 0이 아닌 경우) "Odd"를 return 합니다.


# 📘 그 외의 풀이

### 1. 삼항 연산자 이용하기

#### 삼항 연산자
```text/plain
조건식 ? return1 : return2;
```
> 💡 삼항 연산자는 물음표(?) 앞의 조건식에 따라 결과값이 참(true)이면 return1을 반환하고, 결과값이 거짓(false)이면 Return2를 반환한다.

```java
public class Solution {
    String solution(int num) {
        return num % 2 == 0 ? "Even": "Odd";
    }

    public static void main(String[] args) {
        
        Solution result = new Solution();
        
        // result값 출력
        System.out.println("결과 : " + result.solution(3));
        System.out.println("결과 : " + result.solution(4));
    }
}
```
보시면 solution 메서드의 길이가 대폭 줄어든 것을 볼 수 있습니다.
if-else문을 사용할 때보다 훨씬 간결하게 사용할 수 있습니다.
