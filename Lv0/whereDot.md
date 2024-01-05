# 점의 위치 구하기

## 📌 문제 설명

사분면은 한 평면을 x축과 y축을 기준으로 나눈 네 부분입니다. 사분면은 아래와 같이 1부터 4까지 번호를매깁니다.

- x 좌표와 y 좌표가 모두 양수이면 제1사분면에 속합니다.
- x 좌표가 음수, y 좌표가 양수이면 제2사분면에 속합니다.
- x 좌표와 y 좌표가 모두 음수이면 제3사분면에 속합니다.
- x 좌표가 양수, y 좌표가 음수이면 제4사분면에 속합니다.

x 좌표 (x, y)를 차례대로 담은 정수 배열 dot이 매개변수로 주어집니다. 좌표 dot이 사분면 중 어디에 속하는지 1, 2, 3, 4 중 하나를 return 하도록 solution 함수를 완성해주세요.

### 제한 조건

- dot의 길이 = 2
- dot[0]은 x좌표를, dot[1]은 y좌표를 나타냅니다
- -500 ≤ dot의 원소 ≤ 500
- dot의 원소는 0이 아닙니다.


### 입출력 예

| dot     | result |
| ------- | ------ |
| [2, 4]  | 1      |
| [-7, 9] | 2      |

# 🧐 접근

조건문을 사용해서 각 조건에 맞는 결과 반환

```java
class Solution {
    public int solution(int[] dot) {
        if (dot[0] > 0 && dot[1] > 0) return 1;
        else if (dot[0] < 0 && dot[1] > 0) return 2;
        else if (dot[0] < 0 && dot[1] < 0) return 3;
        else return 4;
    }
}
```

# 💡 풀이

if문을 사용해서 각 조건에 부합하는 결과를 반환했다.

# 📘 그 외의 풀이

###  1. 조건문2

> 💡 이렇게 사용할경우 어떤 경우던지 조건문을 2번 수행하게 된다.

```java
class Solution {
    public int solution(int[] dot) {
        int answer = 0;
        if(dot[0] > 0) 
            if(dot[1] > 0) answer = 1;
            else answer = 4;
        else 
            if(dot[1] > 0) answer = 2;
            else answer = 3;


        return answer;
    }
}
```