# Week 1 — Question 1: Two Sum

## Problem

Given an integer array `nums` and an integer `target`, return the indices of the two numbers whose values add up to `target`.

You may assume that:

- Exactly one valid answer exists.
- The same element cannot be used twice.
- The answer can be returned in any order.

## Examples

```text
Input:  nums = [2, 7, 11, 15], target = 9
Output: [0, 1]
Explanation: nums[0] + nums[1] = 2 + 7 = 9
```

```text
Input:  nums = [3, 2, 4], target = 6
Output: [1, 2]
```

```text
Input:  nums = [3, 3], target = 6
Output: [0, 1]
```

## Constraints

- `2 <= nums.length <= 10^4`
- `-10^9 <= nums[i] <= 10^9`
- `-10^9 <= target <= 10^9`

## Your task

1. Write a brute-force solution first.
2. State its time and space complexity.
3. Improve it using a `HashMap`.
4. Test it with the examples and at least two edge cases.

## Java method signature

```java
public int[] twoSum(int[] nums, int target) {
    
    Map<Integer, Integer> frequency = new HashMap<>();

    for(int i=0; i<nums.length; i++)
    {
        int rem = target - nums[i];

        if(frequency.containsKey(rem))
        {
            return new int[]{frequency.get(rem), i};
        }

        frequency.put(nums[i],i);
    }

    return new int[]{0,0};
}
```

## Edge cases to test

- The matching values are duplicates: `[3, 3]`, target `6`
- Negative values: `[-3, 4, 3, 90]`, target `0`
- The matching pair is at the end of the array

## Hint

For each number, ask: what value would complete the target sum? Store values you have already seen so that this lookup is fast.
