# rny_string

## 📌 문제 설명

'm'과 "rn"이 모양이 비슷하게 생긴 점을 활용해 문자열에 장난을 하려고 합니다. 문자열 rny_string이 주어질 때, rny_string의 모든 'm'을 "rn"으로 바꾼 문자열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ rny_string의 길이 ≤ 100
- rny_string은 영소문자로만 이루어져 있습니다

### 입출력 예

| rny_string    | result          |
| ------------- | --------------- |
| "masterpiece" | "rnasterpiece"  |
| "programmers" | "prograrnrners" |
| "jerry"       | "jerry"         |
| "burn"        | "burn"          |

# 🧐 접근

`replace()`를 사용해서 문자열 교환

```java
class Solution {
    public String solution(String rny_string) {
        return rny_string.replace("m", "rn");
    }
}
```

# 💡 풀이

`replace()`문자열 메서드를 사용해서 `"m"`을 `"rn"`으로 대체

# 📘 그 외의 풀이

### ==================