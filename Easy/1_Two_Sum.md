# 1. Two Sum

## 📌 문제 설명

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

### 제한 조건

- 2 <= nums.length <= 10^4
- -10^9 <= nums[i] <= 10^9
- -10^9 <= target <= 10^9
- Only one valid answer exists.
- Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?
-

### 입출력 예

| Example 1:

> Input: nums = [2,7,11,15], target = 9 <br />
> Output: [0,1] <br />
> Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

| Example 2:

> Input: nums = [3,2,4], target = 6 <br />
> Output: [1,2]

| Example 3:

> Input: nums = [3,3], target = 6
> Output: [0,1]

# 🧐 접근

반복문을 통해서 배열내의 원소값들을 더하기

```java
class Solution {
  public int[] twoSum(int[] nums, int target) {
    int[] result = new int[2];
    for(int i = 0; i < nums.length; i++) {
      for(int j = i+1; j < nums.length; j++) {
        if(nums[i] + nums[j] == target) {
          result[0] += i;
          result[1] += j;
          break;
        }
      }
    }
    return result;
  }
}
```

# 💡 풀이

for 반복문을 사용해서 배열의 원소값들을 answer에 더해주고, 배열의 길이로 나누어 평균을 구함

# 개선하기

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> numMap = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (numMap.containsKey(complement)) {
                return new int[] { numMap.get(complement), i };
            }
            numMap.put(nums[i], i);
        }

        return new int[2];
    }
}
```

# 📘 그 외의 풀이

### 1. stream 사용

> 💡 stream을 사용해서 배열의 원소값들을 더하고, 평균을 구함

```java
import java.util.Arrays;

class Solution {
    public double solution(int[] numbers) {
        return Arrays.stream(numbers).average().orElse(0);
    }
}
```
