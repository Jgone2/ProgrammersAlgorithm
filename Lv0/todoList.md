# 할 일 목록

## 📌 문제 설명

오늘 해야 할 일이 담긴 문자열 배열 todo_list와 각각의 일을 지금 마쳤는지를 나타내는 boolean 배열 finished가 매개변수로 주어질 때, todo_list에서 아직 마치지 못한 일들을 순서대로 담은 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ todo_list의 길이 1 ≤ 100
- 2 ≤ todo_list의 원소의 길이 ≤ 20
  - todo_list의 원소는 영소문자로만 이루어져 있습니다.
  - todo_list의 원소는 모두 서로 다릅니다.
- finished[i]는 true 또는 false이고 true는 todo_list[i]를 마쳤음을, false는 아직 마치지 못했음을 나타냅니다.
- 아직 마치지 못한 일이 적어도 하나 있습니다.

### 입출력 예

| todo_list                                                  | finished             | result                          |
| ---------------------------------------------------------- | - | ------ |
| ["problemsolving", "practiceguitar", "swim", "studygraph"] | [true, false, true, false] | ["practiceguitar", "studygraph"] |

# 🧐 접근

false의 갯수를 알 수 없으니 ArrayList에 담아서 배열로 변환

```java
import java.util.ArrayList;
class Solution {
    public String[] solution(String[] todo_list, boolean[] finished) {
        ArrayList<String> list = new ArrayList<>();
        for (int i = 0; i < todo_list.length; i++) {
            if (!finished[i]) list.add(todo_list[i]);
        }
        return list.toArray(String[]::new);
    }
}
```

# 💡 풀이

false의 갯수를 알 수 없으니 ArrayList를 생성하고 finished배열의 인덱스가 false일때 todo_list에서 동일 인덱스의 값을 추가

# 📘 그 외의 풀이

### 1. split

> 💡 String객체에 조건에 부합할 시 해당 값과 `,`를 추가해주고 `,`를 기준으로 문자열을 나눠 배열화. String 객체를 수정할때마다 새로운 String객체가 생성되므로 `StringBuilder`를 사용할 수 있을 것 같다.


```java
class Solution {
    public String[] solution(String[] todo_list, boolean[] finished) {
        String str = "";
        for(int i=0; i<finished.length; i++){
            str = finished[i]==false ? str+todo_list[i]+"," : str;
        }

        return str.split(",");
    }
}
```