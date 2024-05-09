# 음양 더하기

## 📌 문제 설명

어떤 정수들이 있습니다. 이 정수들의 절댓값을 차례대로 담은 정수 배열 absolutes와 이 정수들의 부호를 차례대로 담은 불리언 배열 signs가 매개변수로 주어집니다. 실제 정수들의 합을 구하여 return 하도록 solution 함수를 완성해주세요.

### 제한 조건

- absolutes의 길이는 1 이상 1,000 이하입니다.
  - absolutes의 모든 수는 각각 1 이상 1,000 이하입니다.
- signs의 길이는 absolutes의 길이와 같습니다.
  - signs[i] 가 참이면 absolutes[i] 의 실제 정수가 양수임을, 그렇지 않으면 음수임을 의미합니다.

### 입출력 예

| absolutes  | signs                | return |
| ---------- | -------------------- | ------ |
| [4, 7, 12] | [true, false, true]  | 9      |
| [1, 2, 3]  | [false, false, true] | 0      |

# 🧐 접근

반복문 내에서 조건문을 사용해서 조건에 맞는 연산식을 수행할 수 있도록 하자.

```java
class Solution {
    public int solution(int[] absolutes, boolean[] signs) {
        int answer = 0;
        for (int i = 0; i < absolutes.length; i++) {
            if (signs[i] == true) answer += absolutes[i];
            else answer -= absolutes[i];
        }
        return answer;
    }
}
```

# 💡 풀이

배열 absolutes와 signs의 value들이 동일비교되어야하므로 반복문을 사용한 후 조건문을 사용해서 배열 `signs[i]`의 값에 따라 배열 `absolutes[i]`의 값의 연산을 수행

# 📘 그 외의 풀이

### 1. 삼항연산자 사용

> 💡 삼항 연산자를 사용해서 조건에 따라 삼항 연산자를 사용하여 `1` 혹은 `-1`로 값을 지정한 다음 배열 `absolutes[i]`의 값과 곱하여 절대값에 음양을 추가해준 후에 answer에 더해준다.

```java
class Solution {
    public int solution(int[] absolutes, boolean[] signs) {
        int answer = 0;
        for (int i=0; i<signs.length; i++)
            answer += absolutes[i] * (signs[i]? 1: -1);
        return answer;
    }
}
```

> 💡 삼항 연산자의 조건에 따라 배열 `absolutes[i]`의 값에 `-`를 붙여준 후 연산 수행

```java
class Solution {
    public int solution(int[] absolutes, boolean[] signs) {
        int answer = 0;
        for (int i = 0; i < absolutes.length; i++) {
            answer += (signs[i]) ? absolutes[i] : -absolutes[i];
        }
        return answer;
    }
}
```