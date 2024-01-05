# 문자열안에 문자열

## 📌 문제 설명

문자열 str1, str2가 매개변수로 주어집니다. str1 안에 str2가 있다면 1을 없다면 2를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ str1의 길이 ≤ 100
- 1 ≤ str2의 길이 ≤ 100
- 문자열은 알파벳 대문자, 소문자, 숫자로 구성되어 있습니다.


### 입출력 예
| str1                     | str2   | result |
| ------------------------ | ------ | ------ |
| "ab6CDE443fgh22iJKlmn1o" | "6CD"  | 1      |
| "ppprrrogrammers"        | "pppp" | 2      |
| "AbcAbcA"                | "AAA"  | 2      |

# 🧐 접근

문자열을 비교해주는 메서드를 사용하자

```java
class Solution {
    public int solution(String str1, String str2) {
        return str1.contains(str2) ? 1 : 2;
    }
}
```

# 💡 풀이

`contains()`를 사용해서 두 문자열을 비교

# 📘 그 외의 풀이

###  1. 반복문을 사용해 직접 비교

> 💡 반복문을 사용해 직접 비교

```java
class Solution {
    public int solution(String str1, String str2) {
        int len1 = str1.length();
        int len2 = str2.length();

        if (len2 > len1) {
            return 2;
        }

        for (int i = 0; i < len1 - len2 + 1; i++) {
            if (str1.charAt(i) == str2.charAt(0)) {
                for (int j = 0; j < len2; j++) {
                    if (str1.charAt(i + j) == str2.charAt(j)) {
                        if (j == len2 - 1) {
                            return 1;
                        }
                        continue;
                    }

                    break;
                }
            }
        }

        return 2;
    }
}
```