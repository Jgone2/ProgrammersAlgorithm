# 덧셈식 출력하기

## 📌 문제 설명

두 정수 a, b가 주어질 때 다음과 같은 형태의 계산식을 출력하는 코드를 작성해 보세요.

```text/plain
a + b = c
```


### 제한 조건

- 1 ≤ a, b ≤ 100

### 입출력 예

입력 #1

```text/plain
4 5
```

출력 #1

```text/plain
4 + 5 = 9
```

# 🧐 접근

Just 출력.

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();

        System.out.println(a + " + " + b + " = " + (a + b));
    }
}
```

# 💡 풀이

진짜 그냥 출력

# 📘 그 외의 풀이

### ===============