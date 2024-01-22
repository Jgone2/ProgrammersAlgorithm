# 대문자와 소문자

## 📌 문제 설명

문자열 my_string이 매개변수로 주어질 때, 대문자는 소문자로 소문자는 대문자로 변환한 문자열을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 1,000
- my_string은 영어 대문자와 소문자로만 구성되어 있습니다.

### 입출력 예

| my_string    | result       |
| ------------ | ------------ |
| "cccCCC"     | "CCCccc"     |
| "abCdEfghIJ" | "ABcDeFGHij" |

# 🧐 접근

`Character.isUpperCase()`와 `Character.isLowerCase()`를 사용

```java
class Solution {
    public String solution(String my_string) {
        StringBuilder sb = new StringBuilder();
        for(char c : my_string.toCharArray()) {
            if (Character.isUpperCase(c)) sb.append(Character.toLowerCase(c));
            else sb.append(Character.toUpperCase(c));
        }
        return sb.toString();
    }
}
```

# 💡 풀이

반복문 내에서 조건문을 사용해서 `Character.isUpperCase()`일 때 소문자로 반대일 때 대문자로 변환 한 값을 `StringBuilder`객체 sb에 할당.
sb를 String객체로 변환하여 반환

# 📘 그 외의 풀이

### 1. ASCII 코드 사용

> 💡 아스키 코드를 사용해서 대 소문자 구분 후 변환

```java
class Solution {
    public String solution(String s) {
        String answer = "";

        for(int i=0;i<s.length();i++){
            if(s.charAt(i)>=97 && s.charAt(i)<=122){
                answer += (char)(s.charAt(i)-32);
            } else if(s.charAt(i)>=65 && s.charAt(i)<=90){
                answer += (char)(s.charAt(i)+32);
            } else {
                answer += s.charAt(i);
            }
        }

        return answer;
    }
}
```