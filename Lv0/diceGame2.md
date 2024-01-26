# 주사위 게임 2

## 📌 문제 설명

1부터 6까지 숫자가 적힌 주사위가 세 개 있습니다. 세 주사위를 굴렸을 때 나온 숫자를 각각 a, b, c라고 했을 때 얻는 점수는 다음과 같습니다.

- 세 숫자가 모두 다르다면 a + b + c 점을 얻습니다.
- 세 숫자 중 어느 두 숫자는 같고 나머지 다른 숫자는 다르다면 (a + b + c) × (a2 + b2 + c2 )점을 얻습니다.
- 세 숫자가 모두 같다면 (a + b + c) × (a2 + b2 + c2 ) × (a3 + b3 + c3 )점을 얻습니다.

세 정수 a, b, c가 매개변수로 주어질 때, 얻는 점수를 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- a, b, c는 1이상 6이하의 정수입니다.

### 입출력 예

| a | b | c | result |
| - | - | - | ------ |
| 2 | 6 | 1 | 9      |
| 5 | 3 | 3 | 473    |
| 4 | 4 | 4 | 110592 |

# 🧐 접근

각 조건에 맞는 값 반환

```java
class Solution {
    public int solution(int a, int b, int c) {
        if (a == b && a == c) return (a + b + c) * (int)(Math.pow(a, 2) + Math.pow(b, 2) + Math.pow(c, 2)) * (int)(Math.pow(a, 3) + Math.pow(b, 3) + Math.pow(c, 3));
        if (a == b || a == c || b == c) return (a + b + c) * (int)(Math.pow(a, 2) + Math.pow(b, 2) + Math.pow(c, 2));
        return a + b + c;
    }
}
```

# 💡 풀이

접근법과 동일

# 📘 그 외의 풀이

### 1. 재귀함수

> 💡 재귀를 사용하여 풀이

```java
class Solution {
    public int solution(int a, int b, int c) {
        int answer = 1;

        int count = 1;
        if(a == b || a == c || b == c) {
            count++;
        }

        if(a == b && b == c) {
            count++;
        }

        for(int i = 1; i <= count; i++) {
            answer *= (pow(a,i)+pow(b,i)+pow(c,i));
        }

        return answer;
    }

    private int pow(int a, int b) {
        if(b == 0) return 1;
        return a * pow(a, b-1);
    }
}
```