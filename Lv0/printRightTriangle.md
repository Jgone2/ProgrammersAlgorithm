# 직각삼각형 출력하기

## 📌 문제 설명

`*`의 높이와 너비를 1이라고 했을 때, `*`을 이용해 직각 이등변 삼각형을 그리려고합니다. 정수 n 이 주어지면 높이와 너비가 n 인 직각 이등변 삼각형을 출력하도록 코드를 작성해보세요.

### 제한 조건

- 1 ≤ n ≤ 10

### 입출력 예

입력 #1
```text/plain
3
```
출력 #1
```text/plain
*
**
***
```

# 🧐 접근

`repeat()`사용

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();

        for (int i =  1; i <= n; i++) {
            System.out.println("*".repeat(i));
        }
    }
}
```

# 💡 풀이

반복문을 통해 1부터 n이하의 수에서 i만큼 별을 출력하는 연산을 반복 수행한다.

# 📘 그 외의 풀이

### ==================