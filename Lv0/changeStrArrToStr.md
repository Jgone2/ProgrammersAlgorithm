# 문자 리스트를 문자열로 변환하기

## 📌 문제 설명

문자들이 담겨있는 배열 arr가 주어집니다. arr의 원소들을 순서대로 이어 붙인 문자열을 return 하는 solution함수를 작성해 주세요.

### 제한 조건

- 1 ≤ arr의 길이 ≤ 200
  - arr의 원소는 전부 알파벳 소문자로 이루어진 길이가 1인 문자열입니다.

### 입출력 예

| arr           | result |
| ------------- | ------ |
| ["a","b","c"] | "abc"  |

# 🧐 접근

`StringBuilder`객체 사용

```java
class Solution {
    public String solution(String[] arr) {
        StringBuilder sb = new StringBuilder();
        for (String str : arr) sb.append(str);
        return sb.toString();
    }
}
```

# 💡 풀이

반복문을 통해 각 인덱스의 문자열을 추출해 `StringBuilder`의 `append()`메소드를 사용해 문자열 연결.

# 📘 그 외의 풀이

### 1. join()

> 💡 join()메소드를 사용해서 배열을 문자열로 변환할 수 있다.

```java
class Solution {
    public String solution(String[] arr) {
        return String.join("", arr);
    }
}
```