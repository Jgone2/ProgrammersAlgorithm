# 글자 이어 붙여 문자열 만들기

## 📌 문제 설명

문자열 my_string과 정수 배열 index_list가 매개변수로 주어집니다. my_string의 index_list의 원소들에 해당하는 인덱스의 글자들을 순서대로 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ my_string의 길이 ≤ 1,000
- my_string의 원소는 영소문자로 이루어져 있습니다.
- 1 ≤ index_list의 길이 ≤ 1,000
- 0 ≤ index_list의 원소 < my_string의 길이


### 입출력 예
| my_string            | index_list                               | result |
| -------------------- | ---------------------------------------- | ------------- |
| "cvsgiorszzzmrpaqpe" | [16, 6, 5, 3, 12, 14, 11, 11, 17, 12, 7] | "programmers" |
| "zpiaz"              | [1, 2, 0, 0, 3]                          | "pizza"       |

# 🧐 접근

index_list의 첫번째 인덱스부터 순회하며 my_string에서 해당 인덱스에 해당하는 문자를 추출하자

```java
class Solution {
    public String solution(String my_string, int[] index_list) {
        StringBuilder sb = new StringBuilder();
        for (int i : index_list) sb.append(my_string.charAt(i));
        return sb.toString();
    }
}
```

# 💡 풀이

index_list의 요소들을 iter문을 통해 하나씩 추출하고 my_string에서 `charAt()`을 사용해
해당하는 인덱스에 대한 값을 추출해 StringBuilder로 문자열을 완성시킴.

# 📘 그 외의 풀이

###  =============