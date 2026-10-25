# Week 1 — Question 4: Product of Array Except Self

## Problem

Given an integer array `nums`, return an array `result` where `result[i]` is the product of every value in `nums` except `nums[i]`.

Do not use division. Design an algorithm that runs in O(n) time. You may assume each result fits in a signed 32-bit integer.

## Examples

```text
Input:  nums = [1, 2, 3, 4]
Output: [24, 12, 8, 6]
```

```text
Input:  nums = [-1, 1, 0, -3, 3]
Output: [0, 0, 9, 0, 0]
```

## Constraints

- `2 <= nums.length <= 10^5`
- `-30 <= nums[i] <= 30`
- The product of any prefix or suffix of `nums` fits in a signed 32-bit integer.

## Your task

1. Implement the method below without using division.
2. State its time and space complexity. Treat the returned array as output space.
3. Test it with the examples and at least two additional edge cases, including an input with multiple zeroes.

## Java method signature

```java
public int[] productExceptSelf(int[] nums);
```
