# 숫자 찾기

## 📌 문제 설명

정수 num과 k가 매개변수로 주어질 때, num을 이루는 숫자 중에 k가 있으면 num의 그 숫자가 있는 자리 수를 return하고 없으면 -1을 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 0 < num < 1,000,000
- 0 ≤ k < 10
- num에 k가 여러 개 있으면 가장 처음 나타나는 자리를 return 합니다.

### 입출력 예

| num    | k | result |
| ------ | - | ------ |
| 29183  | 1 | 3      |
| 232443 | 4 | 4      |
| 123456 | 7 | -1     |

# 🧐 접근

정수를 문자열로 변환후 한 자리씩 추출해서 반복문 연산 수행

```java
class Solution {
    public int solution(int num, int k) {
        String strNum = Integer.toString(num);
    for (int i = 0; i < strNum.length(); i++) {
        if (strNum.charAt(i) - '0' == k) return ++i;
    }
    return -1;
    }
}
```

# 💡 풀이

정수를 문자열로 변환하고 해당 문자열을 가지고 반복문을 수행.
반복문 내에서 문자열의 인덱스 1개씩 순서대로 추출하여 '0'을 뺀 값이 k와 같다면 i값에 1을 더한 값을 반환.

해당되는 값이 없을 시 -1 반환

# 📘 그 외의 풀이

### 1. indexOf()

> 💡 `indexOf()`를 사용해 해당 값의 인덱스를 찾을 수 있다. 인덱스가 아닌 1, 2, 3과 같이 추출해야하므로 num앞에 `"-"`를 추가함을 알 수 있다.

```java
class Solution {
    public int solution(int num, int k) {
        return ("-" + num).indexOf(String.valueOf(k));
    }
}
```