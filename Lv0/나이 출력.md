# 나이 출력

## 📌 문제 설명

머쓱이는 40살인 선생님이 몇 년도에 태어났는지 궁금해졌습니다. 나이 age가 주어질 때, 2022년을 기준 출생 연도를 return 하는 solution 함수를 완성해주세요.

### 제한 조건

- 0 < age <= 120
- 나이는 태어난 연도에 1살이며 1년마다 1씩 증가합니다.

### 입출력 예

| age | result |
| --- | ------ |
| 40  | 1983   |
| 23  | 2000   |

# 🧐 접근

2022년에서 나이를 뺀다.

```java
class Solution {
    public int solution(int age) {
        return 2022 - (age - 1);
    }
}
```

# 💡 풀이

2022년에서 나이를 뺀 후 태어난 연도에 1살로 계산하기 때문에 -1을 해줌.

# 📘 그 외의 풀이

### 1. `+` 연산자 사용

> 💡 `+`연산자를 사용해서 구현할 수도 있다.

```java
class Solution {
    public int solution(int age) {
        return 2022 - age + 1;
    }
}
```
