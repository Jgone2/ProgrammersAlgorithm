# 문자열 돌리기

## 📌 문제 설명

문자열 str이 주어집니다.
문자열을 시계방향으로 90도 돌려서 아래 입출력 예와 같이 출력하는 코드를 작성해 보세요.

### 제한 조건

- 1 ≤ str의 길이 ≤ 10

### 입출력 예

입력 #1

```text/plain
abcde
```

출력 #1

```text/plain
a
b
c
d
e
```

# 🧐 접근

하나씩 출력하기

```java
import java.util.Scanner;
public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        
        for (char c : a.toCharArray()) {
            System.out.println(c);
        }
    }
}
```

# 💡 풀이

`println()` 사용해 하나씩 출력했다.

# 📘 그 외의 풀이

### ==============