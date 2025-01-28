# 문자 반복 출력하기

## 📌 문제 설명

문자열 my_string과 정수 n이 매개변수로 주어질 때, my_string에 들어있는 각 문자를 n만큼 반복한 문자열을 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 2 ≤ my_string 길이 ≤ 5
- 2 ≤ n ≤ 10
- "my_string"은 영어 대소문자로 이루어져 있습니다.

### 입출력 예

| my_string | n | result            |
| --------- | - | ----------------- |
| "hello"   | 3 | "hhheeellllllooo" |

# 🧐 접근

`StringBuilder`를 사용해서 풀이

```java
class Solution {
    public String solution(String my_string, int n) {
        StringBuilder sb = new StringBuilder();
        for (char c : my_string.toCharArray()) {
            for (int i = 0; i < n; i++) {
                sb.append(c);
            }
        }
        return sb.toString();
    }
}
```

# 💡 풀이

입력받은 문자열 `my_string`을 char형의 배열로 반환받아 iter문을 사용해 sb에 문자열 하나씩을 추가해준다.
다만 `StringBuilder`의 메소드를 사용해서 풀이하려고 사용했으나 `append`만 사용한 점은 아쉬움이 남는다.
`repeat()`을 사용했다면 이중 반복문을 사용안해도 됐을 텐데 말이다. 

```java
class Solution {
    public String solution(String my_string, int n) {
        StringBuilder sb = new StringBuilder();
        for (char c : my_string.toCharArray()) {
            sb.append((c + "").repeat(n));
        }
        return sb.toString();
    }
}
```

`repeat()` 메소드는 `String` 클래스의 메소드이므로, char타입의 변수로 반복문을 수행하는 과정에서 풀이하기 위해서 아래와 같이 변수 c를 문자열로 변환해주는 과정이 필요하다.
```java
sb.append((c + "")).repeat(n)); // 방법 1
sb.append(Character.toString(c).repeat(n)); // 방법2
sb.append(String.valueOf(c).repeat(n)); // 방법 3
```

반복문에서 다음과 같이 `length()`를 사용해서 수행한다 하더라도 문자열에서 `charAt()`을 사용해서 문자를 추출해야하기 때문에 결국 char형변수를 문자열로 변환해주는 과정은 동일하게 필요하다.
```java
for (int i = 0; i < my_string.length(); i++) {...}
```

# 📘 그 외의 풀이

### 1. `split()`메소드 사용

> 💡 String 클래스 메소드인 `split()`메소드를 사용해서 문자열 배열을 생성한 후 반복문 연산 수행

```java
class Solution {
    public String solution(String my_string, int n) {
        String answer = "";
        String[] str = my_string.split("");
        for(int i=0; i<my_string.length(); i++){
            answer += str[i].repeat(n);
        }
        return answer;
    }
}
```

### 2. `substring()`메소드 사용

> 💡 형변환 없이 문자열 그대로 문자열 메소드를 사용해서 연산 수행
> ❗️ 그러나 `substring()`를 사용함녀 새로운 String객체를 생성하기 때문에, 반복문 내에서 호출하지 않는 것이 좋다.

```java
class Solution {
    public String solution(String my_string, int n) {
        String answer = "";

        for(int i=0; i<my_string.length(); i++){
            for(int j = 0; j<n; j++){
                answer += my_string.substring(i, i+1);
            }
        }
        return answer;
    }
}
```