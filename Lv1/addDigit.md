# 자릿수 더하기

## 📌 문제 설명

자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.
예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.

### 제한 조건

- N의 범위 : 100,000,000 이하의 자연수

### 입출력 예

| num | return |
| --- | ------ |
| 123 | 6      |
| 987 | 24     |

# 🧐 접근

String클래스로 형변환하여 한자리씩 분리 후 다시 형변환을 하자.

```java
import java.util.*;

public class Solution {
    public int solution(int n) {
        int answer = 0;

        String str = Integer.toString(n); //int n을 String으로 변환

        for(int i = 0; i<str.length(); i++){
            answer += Integer.parseInt(str.substring(i, i+1));
        }

        return answer;
    }
}
```

# 💡 풀이

먼저 한자리씩 분리하기 위해 toString()메서드를 사용하여 String클래스로 형변환을 합니다.
그 후에 반복문과 substring()메서드를 사용하여 한자리씩 answer에 더해줍니다.

> 💡 형변환을 진행하지 않고 문제를 해결할 수 있을 것 같은데,, 불필요한 형변환을 진행하면서 최적화되지 못한 풀이같다.. 더 공부해야겠다 ㅜㅜ

# 📘 그 외의 풀이

### 1. While문 사용

#### 1. ---

> 💡

```java
import java.util.*;

public class Solution {
    public int solution(int n) {
        int answer = 0;
        while(n>0){

            answer += n%10;
            n /= 10;

        }

        // [실행] 버튼을 누르면 출력 값을 볼 수 있습니다.
        System.out.println("Hello Java");

        return answer;
    }
}
```

#### 2. ---

> 💡

```java
import java.util.*;

public class Solution {
    public int solution(int n) {
        int answer = 0;

        while (n != 0) {
            answer += n % 10;
            n /= 10;
        }

        return answer;
    }
}
```

### 2. Math.log10()메서드 사용

> 💡

```java
import java.util.*;

public class Solution {
    public int solution(int n) {
        int answer = 0;
        int len = (int)Math.log10(n)+1;
        for(int i = 0; i < len; i++) {
            answer += n%10;
            n = n/10;
        }
        return answer;
    }
}
```

### 3. 비슷한 풀이

> 💡

```java
import java.util.*;

public class Solution {
    public int solution(int n) {
        int answer = 0;
        String[] array = String.valueOf(n).split("");
        for(String s : array){
            answer += Integer.parseInt(s);
        }
        return answer;
    }
}
```
