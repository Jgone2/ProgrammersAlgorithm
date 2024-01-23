# 5명씩

## 📌 문제 설명

최대 5명씩 탑승가능한 놀이기구를 타기 위해 줄을 서있는 사람들의 이름이 담긴 문자열 리스트 names가 주어질 때, 앞에서 부터 5명씩 묶은 그룹의 가장 앞에 서있는 사람들의 이름을 담은 리스트를 return하도록 solution 함수를 완성해주세요. 마지막 그룹이 5명이 되지 않더라도 가장 앞에 있는 사람의 이름을 포함합니다.

### 제한 조건

- 5 ≤ names의 길이 ≤ 30
- 1 ≤ names의 원소의 길이 ≤ 10
- names의 원소는 영어 알파벳 소문자로만 이루어져 있습니다.

### 입출력 예

| names                                                      | result                  |
| ---------------------------------------------------------- | ----------------------- |
| ["nami", "ahri", "jayce", "garen", "ivern", "vex", "jinx"] | ["nami", "vex"] |

# 🧐 접근

반복문 사용

```java
class Solution {
    public String[] solution(String[] names) {
        String[] answer = new String[(names.length + 4) / 5];
        int idx = 0;
        for (int i = 0; i < answer.length; i++) {
            answer[i] = names[idx];
            idx += 5;
        }
        return answer;
    }
}
```

# 💡 풀이

5명이 채워지지 않아도되기때문에 매개변수 `names`의 길이에 4를 더한 다음 5로 나눈 값을 배열`answer`의 길이로 초기화한다. 반복문을 수행하면서 idx값을 5씩 더하면서 5명씩 묶어 선두에 있는 인덱스를 추출

# 📘 그 외의 풀이

### ==================