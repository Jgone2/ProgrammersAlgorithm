# 홀짝 구분하기

## 📌 문제 설명

자연수 n이 입력으로 주어졌을 때 만약 n이 짝수이면 "n is even"을, 홀수이면 "n is odd"를 출력하는 코드를 작성해 보세요.

### 제한 조건

- 1 ≤ n ≤ 1,000

### 입출력 예

입력 #1

```text/plain
100
```

출력 #1

```text/plain
100 is even
```

입력 #2

```text/plain
1
```

출력 #2

```text/plain
1 is odd
```


# 🧐 접근

삼항연산자를 이용해 출력하면 된다.

```java
import java.util.Scanner;
public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        System.out.print(String.format("%d is %s", n, (n % 2 == 0) ? "even" : "odd"));
    }
}
```

# 💡 풀이

`String.format()`을 사용해서 위 처럼 출력해도 되고 아래 방식으로 출력해도 무관하다.
```java
System.out.print(n + " is " + ((n % 2 == 0) ? "even" : "odd"));
```

# 📘 그 외의 풀이

### ==================