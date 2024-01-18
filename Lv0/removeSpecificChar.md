# 특정 문자 제거하기

## 📌 문제 설명

문자열 my_string과 문자 letter이 매개변수로 주어집니다. my_string에서 letter를 제거한 문자열을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 100
- letter은 길이가 1인 영문자입니다.
- my_string과 letter은 알파벳 대소문자로 이루어져 있습니다.
- 대문자와 소문자를 구분합니다.

### 입출력 예

| my_string | letter | result  |
| --------- | ------ | ------- |
| "abcdef"  | "f"    | "abcde" |
| "BCBdbe"  | "B"    | "Cdbe"  |

# 🧐 접근

`replaceAll()`사용

```java
class Solution {
    public String solution(String my_string, String letter) {
        return my_string.replaceAll(letter, "");
    }
}
```

# 💡 풀이

`replaceAll()`메서드를 사용해 letter에 속한 문자를 ""로 대체해 삭제처리해준다.
정규표현식과 같은 것을 사용하지 않기에 `replace()`메서드를 사용해도 무방하다.

# 📘 그 외의 풀이

### ==================