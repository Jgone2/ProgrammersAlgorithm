# 숨어있는 숫자의 덧셈(1)

## 📌 문제 설명

문자열 my_string이 매개변수로 주어집니다. my_string안의 모든 자연수들의 합을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 1,000
- my_string은 소문자, 대문자 그리고 한자리 자연수로만 구성되어있습니다.

### 입출력 예

| my_string       | result |
| --------------- | ------ |
| "aAb1B2cC34oOp" | 10     |
| "1a2b3c4d123"   | 16     |

# 🧐 접근

pattern과 matcher를 사용해서 숫자를 찾아내자

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
class Solution {
    public int solution(String my_string) {
        int answer = 0;
        Pattern pattern = Pattern.compile("\\d");
        Matcher matcher = pattern.matcher(my_string);
        while(matcher.find()) answer += Integer.parseInt(matcher.group());
        return answer;
    }
}
```

# 💡 풀이

`pattern`을 사용해서 해당 정규표현식 패턴을 사용해서 패턴 추출을 할 수 있도록 패턴 생성.
`matcher`를 사용해서 my_string에서 패턴에 일치하는 부분을 추출
루프를 사용해서 문자열에서 추출된 숫자를 정수형으로 형변환 후 answer에 더한다.

해당 기능을 새롭게 알게되어 사용 해봤는데 `Pattern`과 `Matcher`를 사용하지 않는다면 다음과 같이 풀이 할 수 있다.

```java
class Solution {
    public int solution(String my_string) {
        int answer = 0;
        for (char c : my_string.toCharArray()) {
            if (Character.isDigit(c)) answer += Character.getNumericValue(c);
        }
        return answer;
    }
}
```

위의 코드는 문자열my_string을 char형 배열로 변환 후 루프문을 통해 한 글자씩
`isDigit`메서드를 사용해 해당 문자가 숫자(0-9)인지 확인한다. 

조건에 부합할경우 `getNumericValue`를 사용해서 정수형으로 변환해 answer에 더해준다.

# 📘 그 외의 풀이

### ==================