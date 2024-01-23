# 배열의 원소 삭제하기

## 📌 문제 설명

정수 배열 arr과 delete_list가 있습니다. arr의 원소 중 delete_list의 원소를 모두 삭제하고 남은 원소들은 기존의 arr에 있던 순서를 유지한 배열을 return 하는 solution 함수를 작성해 주세요.

### 제한 조건

- 1 ≤ arr의 길이 ≤ 100
- 1 ≤ arr의 원소 ≤ 1,000
- arr의 원소는 모두 서로 다릅니다.
- 1 ≤ delete_list의 길이 ≤ 100
- 1 ≤ delete_list의 원소 ≤ 1,000
- delete_list의 원소는 모두 서로 다릅니다.


### 입출력 예

| arr                       | delete_list                 | result     |
| ------------------------- | ----------------------------| ---------- |
| [293, 1000, 395, 678, 94] | [94, 777, 104, 1000, 1, 12] | [293, 395, 678]    |
| [110, 66, 439, 785, 1]    | [377, 823, 119, 43]         | [110, 66, 439, 785, 1] |

# 🧐 접근

List로 변환 시킨 다음
`removeAll()`메소드를 사용해서 해당하는 값들을 모두 삭제

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
class Solution {
    public int[] solution(int[] arr, int[] delete_list) {
        List<Integer> listArr = new ArrayList<>();
        for (int e : arr) listArr.add(e);
        
        List<Integer> listDelete = new ArrayList<>();
        for (int e : delete_list)  listDelete.add(e);
        
        listArr.removeAll(listDelete);
        
        int[] answer = new int[listArr.size()];
        for (int i = 0; i < listArr.size(); i++) answer[i] = listArr.get(i);
        
        return answer;
    }
}
```

# 💡 풀이

`removeAll()`메소드를 사용하기 위해 `List`형으로 매개변수들을 저장했다. 그 후 `removeAll()`메소드를 사용해서 `listArr`에서 `listDelete`에 해당하는 원소들을 모두 삭제한 후 배열로 변환해서 반환

# 📘 그 외의 풀이

### hashSet사용

> 💡 HashSet을 사용해서 원소의 확인과 삭제를 수행

```java
import java.util.Arrays;
import java.util.HashSet;

class Solution {
    public int[] solution(int[] arr, int[] delete_list) {
        HashSet<Integer> delete = new HashSet<>();
        for (int del : delete_list)
            delete.add(del);
        return Arrays.stream(arr).filter(i -> !delete.contains(i)).toArray();
    }
}
```