# 모음 제거

## 📌 문제 설명

영어에선 a, e, i, o, u 다섯 가지 알파벳을 모음으로 분류합니다. 문자열 my_string이 매개변수로 주어질 때 모음을 제거한 문자열을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- my_string은 소문자와 공백으로 이루어져 있습니다.
- 1 ≤ my_string의 길이 ≤ 1,000

### 입출력 예

| my_String          | result      |
| ------------------ | ----------- |
| "bus"              | "ABCDEFG"   |  
| "nice to meet you" | "nc t mt y" |

# 🧐 접근

`indexOf()`로 비교

```java
class Solution {
    public String solution(String my_string) {
        StringBuilder sb = new StringBuilder();
        for (char c : my_string.toCharArray()) {
            if("aeiouAEIOU".indexOf(c) == -1) sb.append(c);
        }
        return sb.toString();
    }
}
```

# 💡 풀이

StringBuilder객체를 생성한 후, `toCharArray()`를 통해 문자형 배열로 변화내 반복문을 수행.
반복문에서 해당 인덱스가 모음이 아닐때 StringBuilder객체에 해당 문자를 추가후 반환.

> 💡 indexOf()
> 모음을 String객체로 저장하지 않고 비교하려면 !"aeiouAEIOU".indexOf(c)를 사용하려 했는데, == -1을 사용해야한다고 한다.

# 📘 그 외의 풀이

### 1. replaceAll()

> 💡 replaceAll에서 정규표현식 []를 사용하면 []안에 있는 문자 중 해당되는 것을 찾을 수 있다.
> ❗️ `replace()`에서는 정규 표현식을 사용하지 못한다.

```java
class Solution {
    public String solution(String my_string) {
        String answer = "";
        answer = my_string.replaceAll("[aeiou]", "");
        return answer;
    }
}
```