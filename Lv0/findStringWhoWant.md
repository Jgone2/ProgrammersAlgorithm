# 원하는 문자열 찾기

## 📌 문제 설명

알파벳으로 이루어진 문자열 myString과 pat이 주어집니다. myString의 연속된 부분 문자열 중 pat이 존재하면 1을 그렇지 않으면 0을 return 하는 solution 함수를 완성해 주세요.

단, 알파벳 대문자와 소문자는 구분하지 않습니다.

### 제한 조건

- 1 ≤ myString의 길이 ≤ 100,000
- 1 ≤ pat의 길이 ≤ 300
- myString과 pat은 모두 알파벳으로 이루어진 문자열입니다.

### 입출력 예

| myString  | pat     | result |
| --------- | ------- | ------ |
| "AbCdEfG" | "aBc"	  | 1      |
| "aaAA"    | "aaaaa" | 0      |

# 🧐 접근

`contains()`메소드 사용

```java
class Solution {
    public int solution(String myString, String pat) {
        return myString.toUpperCase().contains(pat.toUpperCase()) ? 1 : 0;
    }
}
```

# 💡 풀이

대소문자를 구분하지 않으니 두 문자열 모두 대문자 또는 소문자로 변환.
`contains()`메소드를 사용하여 문자열 pat이 myString에 포함되는지 확인 후 조건에 맞게 1과 0을 반환

`indexOf()`메소드를 사용해서 풀이할 수도 있는데 다음과 같이 풀이할 수 있다.
```java
class Solution {
    public int solution(String myString, String pat) {
        return myString.toLowerCase().indexOf(pat.toLowerCase()) != -1 ? 1: 0;
    }
}
```

# 📘 그 외의 풀이

### ==================