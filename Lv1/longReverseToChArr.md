# 자연수 뒤집어 배열로 만들기

## 📌 문제 설명

자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 `[5,4,3,2,1]`을 리턴합니다.

### 제한 조건

- n은 10,000,000,000이하인 자연수입니다.

### 입출력 예

| n     | return      |
| ----- | ----------- |
| 12345 | [5,4,3,2,1] |

# 🧐 접근

인자 값을 Stringbuilder로 받아서 해결해보자

```java
class Solution {
    public int[] solution(long n) {
        int[] answer = {};
        String sb = new StringBuilder().append(n).reverse().toString();
        answer = new int[sb.length()];
        for(int i = 0; i < answer.length; i++) {
            answer[i] = sb.charAt(i) - '0';
        }
        return answer;
    }
}
```

# 💡 풀이

문자를 받아서 뒤집고 다시 문자열로 전환해야하기에 Stringbuilder를 사용해서 인자 값을 할당.  
reverse()메서드를 사용해서 입력값을 반대로 뒤집은 후 toString()으로 String형으로 형전환까지 마쳐서 참조변수 sb에 할당.  
그 후 sb길이 만큼 배열의 길이를 설정 후 for문을 돌려 answer에 하나씩 넣기

# 📘 그 외의 풀이

### 1. % 연산자 사용

#### 1.

> 💡

```java
class Solution {
  public int[] solution(long n) {
      String a = "" + n;
        int[] answer = new int[a.length()];
        int cnt=0;

        while(n>0) {
            answer[cnt]=(int)(n%10);
            n/=10;
            System.out.println(n);
            cnt++;
        }
      return answer;
  }
}
```

#### 2.

> 💡

```java
class Solution {
  public int[] solution(long n) {
      int length = Long.toString(n).length();
        int[] answer = new int[length];

        for (int i = 0; i < length; i++) {
            answer[i] = (int) (n % 10);
            n /= 10;
        }

        return answer;
  }
}
```

### 2. 비슷한 풀이

> 💡

```java
import java.util.stream.IntStream;

class Solution {
    public int[] solution(long n) {
        return new StringBuilder().append(n).reverse().chars().map(Character::getNumericValue).toArray();
    }
}
```
