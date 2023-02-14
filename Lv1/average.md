# 평균 구하기

## 📌 문제 설명
정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

### 제한 조건
- arr은 길이 1 이상, 100 이하인 배열입니다.
- arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

### 입출력 예
num | return
--|--
[1, 2, 3, 4] | 2.5
[5, 5] | 5


# 🧐 접근
for문을 사용하여 배열 arr속의 값들을 더하고 배열의 length로 나눠서 평균 출력

```java
class Solution {
    public double solution(int[] arr) {
        double answer = 0;
        for(int n : arr) {
            answer += n;
        }
        answer /= arr.length;
        return answer;
    }
    
    public static void main(String[] args) {
        
        int[] arr1 = {1, 2, 3, 4};
        int[] arr2 = {5, 5};
        Solution result = new Solution();
        
        //result값 출력
        System.out.println("결과: " + result.solution(arr1));    
        System.out.println("결과: " + result.solution(arr2));    
        
    }
}
```

# 💡 풀이
배열 arr 내의 index값을 for문을 사용해서 하나씩 answer에 더합니다.
`/`연산자는 나눗셈 연산자입니다.
arr의 모든 index값의 합을 저장한 answer을 arr배열의 index길이 만큼 나눠서 평균값을 도출합니다.


# 📘 그 외의 풀이

### 1. stream 사용

#### stream()
```text/plain
stream에 대해서 더 공부하고 풀이를 해보자.
```
> 💡 stream에 대해서 더 공부하고 풀이를 해보자.

```java
public class Solution {
    public int solution(int[] array) {
		return (int)Arrays.stream(array).average().orElse(0);
    }

    public static void main(String[] args) {
        int[] arr1 = {1, 2, 3, 4};
        int[] arr2 = {5, 5};
        
        Solution result = new Solution();
        
        // result값 출력
        System.out.println("평균값 : " + result.solution(arr1));
        System.out.println("평균값 : " + result.solution(arr2));
    }
}
```

