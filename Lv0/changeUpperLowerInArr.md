# 배열에서 문자열 대소문자 변환하기

## 📌 문제 설명

문자열 배열 strArr가 주어집니다. 모든 원소가 알파벳으로만 이루어져 있을 때, 배열에서 홀수번째 인덱스의 문자열은 모든 문자를 대문자로, 짝수번째 인덱스의 문자열은 모든 문자를 소문자로 바꿔서 반환하는 solution 함수를 완성해 주세요.

### 제한 조건

- 1 ≤ strArr ≤ 20
  - 1 ≤ strArr의 원소의 길이 ≤ 20
  - strArr의 원소는 알파벳으로 이루어진 문자열 입니다.

### 입출력 예

| srtArr                    | result                    |
| ------------------------- | ------------------------- |
| ["AAA","BBB","CCC","DDD"] | ["aaa","BBB","ccc","DDD"] |
| ["aBc","AbC"]             | ["abc","ABC"]             |

# 🧐 접근

반복문 내에서 조건문 사용

```java
class Solution {
    public String[] solution(String[] strArr) {
        for (int i = 0; i < strArr.length; i++) {
            if (i % 2 == 0) strArr[i] = strArr[i].toLowerCase();
            else strArr[i] = strArr[i].toUpperCase();
        }
        return strArr;
    }
}
```

# 💡 풀이

반복문을 수행하며 각 조건에 맞는 인덱스에서 해당하는 연산 수행

# 📘 그 외의 풀이

### ================