# A로 B 만들기

## 📌 문제 설명

문자열 before와 after가 매개변수로 주어질 때, before의 순서를 바꾸어 after를 만들 수 있으면 1을, 만들 수 없으면 0을 return 하도록 solution 함수를 완성해보세요.

### 제한 조건

- 0 < before의 길이 == after의 길이 < 1,000
- before와 after는 모두 소문자로 이루어져 있습니다.

### 입출력 예

| before  | after   | result |
| ------- | ------- | ------ |
| "olleh" | "hello" | 1      |
| "allpe" | "apple" | 0      |

# 🧐 접근

카운팅 배열(?)을 사용하자

```java
class Solution {
    public int solution(String before, String after) {
        if(before.length() != after.length()) return 0;
        
        int[] cnt = new int[26];
        
        for(char c : before.toCharArray()) cnt[c - 'a']++;
        for(char c : after.toCharArray()) cnt[c - 'a']--;
        
        for(int count : cnt) if(count != 0) return 0;
        return 1;
    }
}
```

# 💡 풀이

문자열 `before`과 `after`의 길이가 다르면 조건이 성립될 수 없으므로 `0`을 반환.
이후 소문자의 개수인 26개의 인덱스를 가진 배열 `cnt`를 생성 후, 문자열 before를 char[] 형식의 배열화하여 해당 요소에서 `a`를 뺀 index값에 +1을 한 후 after에서는 -1을 해준다.
만약에 cnt요소가 하나라도 0이 아니면 해당 조건은 성립할 수 없으므로 `0`을 반환하고 조건을 충족할 시 `1`을 반환

# 📘 그 외의 풀이

### ======================
