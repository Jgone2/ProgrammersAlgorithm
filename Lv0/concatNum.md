# 이어 붙인 수

## 📌 문제 설명

정수가 담긴 리스트 num_list가 주어집니다. num_list의 홀수만 순서대로 이어 붙인 수와 짝수만 순서대로 이어 붙인 수의 합을 return하도록 solution 함수를 완성해주세요.

### 제한 조건

- 2 ≤ num_list의 길이 ≤ 10
- 1 ≤ num_list의 원소 ≤ 9
- num_list에는 적어도 한 개씩의 짝수와 홀수가 있습니다.

### 입출력 예

| num_list        | result |
| --------------- | ------ |
| [3, 4, 5, 2, 1] | 393    |
| [5, 7, 8, 3]    | 581    |

# 🧐 접근

`StringBuilder`사용

```java
class Solution {
    public int solution(int[] num_list) {
        StringBuilder even = new StringBuilder();
        StringBuilder odd = new StringBuilder();
        for(int num : num_list) {
            if(num % 2 == 0) even.append(num);
            else odd.append(num);
        }
        return Integer.parseInt(even.toString()) + Integer.parseInt(odd.toString());
    }
}
```

# 💡 풀이

`StringBuilder`를 사용해서 각 조건에 맞게 나누어 StringBuilder에 정수를 문자열처럼 이어붙여주고,
각각의 StringBuilder객체를 정수형으로 형번환해서 연산.

# 📘 그 외의 풀이

### 1. 10곱하기

> 💡 10을 곱해줌으로써 한자리씩 이어붙여줄 수 있다. 형변환도 필요없으므로 내가 풀이한 방식보다 더 효율적이다.

```java
class Solution {
    public int solution(int[] num_list) {
        int answer = 0;

        int even = 0;
        int odd = 0;

        for(int num : num_list) {
            if(num % 2 == 0) {
                even *= 10;
                even += num;
            } else {
                odd *= 10;
                odd += num;
            }
        }
        answer = even + odd;

        return answer;
    }
}
```