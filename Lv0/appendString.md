# 문자열 붙여서 출력하기

## 📌 문제 설명

두 개의 문자열 str1, str2가 공백으로 구분되어 입력으로 주어집니다.
입출력 예와 같이 str1과 str2을 이어서 출력하는 코드를 작성해 보세요.

### 제한 조건

- 1 ≤ str1, str2의 길이 ≤ 10

### 입출력 예

입력 #1

```text/plain
apple pen
```

출력 #1

```text/plain
applepen
```

입력 #2

```text/plain
Hello World!
```

출력 #2

```text/plain
HelloWorld!
```


# 🧐 접근

진짜 출력만 하면 된다.

```java
import java.util.Scanner;
public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        String b = sc.next();
        System.out.print(a + b);
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### ==================