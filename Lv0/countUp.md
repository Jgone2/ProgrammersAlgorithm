# 카운트 업

## 📌 문제 설명

정수 start_num와 end_num가 주어질 때, start_num부터 end_num까지의 숫자를 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 0 ≤ start_num ≤ end_num ≤ 50

### 입출력 예

| start_num | end_num | result                    |
| --------- | ------- | ------------------------- |
| 3         | 2       | [3, 4, 5, 6, 7, 8, 9, 10] |

# 🧐 접근

반복문을 수행

```java
class Solution {
    public int[] solution(int start_num, int end_num) {
        int[] answer = new int[end_num - start_num + 1];
        int index = 0;
        for(int i = start_num; i <= end_num; i++) {
            answer[index++] = i;
        }
        return answer;
    }
}
```

# 💡 풀이

먼저 반환할 배열`answer`의 크기 지정을 해주고,
반복문을 수행하여 값 할당을 해준다.

stream으로 풀이하면 다음과 같이 작성할 수도 있다.
```java
import java.util.stream.IntStream;
class Solution {
    public int[] solution(int start_num, int end_num) {
        return IntStream.rangeClosed(start_num, end_num).toArray();
    }
}
```

> 💡 반복문 수정
> 불필요하게 index라는 변수를 생성하지 않고 다음과 같이 작성해도 되겠다.
> ```java
> for(int i = 0; i <= answer.length; i++) {
>       answer[i] = start_num++;
>     }
>```

# 📘 그 외의 풀이

### ==================