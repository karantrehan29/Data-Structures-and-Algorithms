# Week 1 — Question 5: Maximum Subarray

## Problem

Given an integer array `nums`, find a non-empty contiguous subarray with the largest possible sum. Return that sum.

## Examples

```text
Input:  nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]
Output: 6
Explanation: The subarray [4, -1, 2, 1] has the largest sum.
```

```text
Input:  nums = [1]
Output: 1
```

```text
Input:  nums = [5, 4, -1, 7, 8]
Output: 23
```

## Constraints

- `1 <= nums.length <= 10^5`
- `-10^4 <= nums[i] <= 10^4`

## Your task

1. Implement the method below.
2. State its time and space complexity.
3. Test it with the examples and at least two additional edge cases, including an all-negative array.

## Java method signature

```java
public int maxSubArray(int[] nums);
```
