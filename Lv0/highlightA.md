# A 강조하기

## 📌 문제 설명

문자열 myString이 주어집니다. myString에서 알파벳 "a"가 등장하면 전부 "A"로 변환하고, "A"가 아닌 모든 대문자 알파벳은 소문자 알파벳으로 변환하여 return 하는 solution 함수를 완성하세요.

### 제한 조건

- 1 ≤ myString의 길이 ≤ 20
  - myString은 알파벳으로 이루어진 문자열입니다.

### 입출력 예

| myString           | result             |
| ------------------ | ------------------ |
| "abstract algebra" | "AbstrAct AlgebrA" |
| "PrOgRaMmErS"      | "progrAmmers"      |

# 🧐 접근

`toLowerCase()`와 `replace()`메소드 사용

```java
class Solution {
    public String solution(String myString) {
        return myString.toLowerCase().replace("a", "A");
    }
}
```

# 💡 풀이

모든 문자열을 소문자로 변환시킨다음 a만 대문자로 재변환

# 📘 그 외의 풀이

### ==================