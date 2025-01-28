# 숫자 비교하기

## 📌 문제 설명

정수 num1과 num2가 매개변수로 주어집니다. 두 수가 같으면 1 다르면 -1을 retrun하도록 solution 함수를 완성해주세요.

### 제한 조건

- 0 < num1 <= 10_000
- 0 < num2 <= 10_000

### 입출력 예

| num1 | num2 | result |
| ---- | ---- | ------ |
| 2    | 3    | -1     |
| 11   | 11   | 1      |
| 7    | 99   | -1     |

# 🧐 접근

조건문을 사용해서 풀이

```java
class Solution {
    public int solution(int num1, int num2) {
        if(num1 == num2) return 1;
        return -1;
    }
}
```

# 💡 풀이

두 수가 같은 조건을 입력해서 1을 return하고, 그 외에는 -1을 return.

# 📘 그 외의 풀이

### 1. 삼항 연산자 사용

> 💡 삼항연산자를 사용해서 한줄로 줄일 수 있다.

```java
class Solution {
    public int solution(int num1, int num2) {
        return (num1 == num2) ? 1 : -1;
    }
}
```
