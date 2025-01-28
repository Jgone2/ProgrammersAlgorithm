# 정수 제곱근 판별

## 📌 문제 설명

임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.
n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.

### 제한 조건

- n은 1이상, 50000000000000 이하인 양의 정수입니다.

### 입출력 예

| n   | return |
| --- | ------ |
| 121 | 144    |
| 3   | -1     |

# 🧐 접근

n의 제곱근을 구하고 그 값을 제곱하여 n과 같으면 x+1의 제곱을 리턴, 아닐 시 -1을 리턴

```java
class Solution {
    public long solution(long n) {
        long answer = 0;
        double x = Math.sqrt(n);
        if(Math.pow(x, 2) == n) {
            answer = (long)Math.pow(x + 1, 2);
        } else {
            answer = -1;
        }
        return answer;
    }
}
```

# 💡 풀이

n의 제곱근을 구하기 위해 Math.sqrt()를 사용하여 n의 제곱근을 구해서 x에 할당.  
할당 후 조건문을 사용해서 x의 제곱의 값이 n과 같을 때 x+1의 제곱의 값을 answer에 할당하고 아닐 시 -1를 할당한 후 리턴

# 📘 그 외의 풀이

### 1. Math.floor()사용

> 💡

```java
class Solution {
  public long solution(long n) {

    double i = Math.sqrt(n);

    return Math.floor(i) == i ? (long) Math.pow(i + 1, 2) : -1;
  }
}
```

### 2. Math 메서드를 사용하지 않고 풀이

> 💡

```java
class Solution {
  public long solution(long n) {
      long answer = 0;

      for (long i = 1; i <= n; i++) {
          if (i * i == n) {
              answer = (i + 1) * (i + 1);
              break;
          }
          else answer = -1;
      }
      return answer;
  }
}
```

### 3. 비슷한 풀이

> 💡

```javaㄴ
class Solution {
  public long solution(long n) {
      if (Math.pow((int)Math.sqrt(n), 2) == n) {
            return (long) Math.pow(Math.sqrt(n) + 1, 2);
        }

        return -1;
  }
}
```
