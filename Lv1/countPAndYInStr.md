# 문자열 내 p와 y의 개수

## 📌 문제 설명

대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

### 제한 조건

- 문자열 s의 길이 : 50 이하의 자연수
- 문자열 s는 알파벳으로만 이루어져 있습니다.

### 입출력 예

| s        | return |
| -------- | ------ |
| "pPooyY" | true   |
| "Pyy"    | false  |

# 🧐 접근

대소문자를 통일한 후 반복문 내에 조건문을 넣어서 ++시키자.

```java
class Solution {
    boolean solution(String s) {
        boolean answer = true;
        s = s.toLowerCase();
        int countP = 0;
        int countY = 0;

        for(int i = 0; i < s.length(); i++) {
            if(s.charAt(i) == 'p') {
                countP++;
            } else if(s.charAt(i) == 'y') {
                countY++;
            }
        }
        answer = (countP == countY) ? true : false;
        return answer;
    }
}
```

# 💡 풀이

먼저 대소문자 통일을 위해 `인자값.toLowerCase()`를 사용하여 소문자로 통일시켜주었습니다.

그 후 `p`와 `y`를 카운트할 변수 2가지를 만들어 주고 문자열의 길이만큼 반복문을 순회하면서 각 자리에 'p'가 위치할 때는 p를 카운트하는 변수를 1증가, 'y'가 위치할 때는 y 를 카운트하는 변수를 1증가.

마지막으로 삼항연산자를 사용하여 두 변수의 값이 같으면 'true', 다르면 'false'를 answer에 대입하여 리턴하도록 했습니다.

# 📘 그 외의 풀이

### 1. filter를 사용하여 한줄로 처리

> 💡

```java
class Solution {
    boolean solution(String s) {
        s = s.toUpperCase();

        return s.chars().filter( e -> 'P'== e).count() == s.chars().filter( e -> 'Y'== e).count();
    }
}
```

### 2. 비슷한 풀이

> 💡

```java
class Solution {
    boolean solution(String s) {
        s = s.toLowerCase();
        int count = 0;

        for (int i = 0; i < s.length(); i++) {

            if (s.charAt(i) == 'p')
                count++;
            else if (s.charAt(i) == 'y')
                count--;
        }

        if (count == 0)
            return true;
        else
            return false;
    }
}
```
