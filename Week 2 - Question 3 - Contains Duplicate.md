# Week 2 — Question 3: Contains Duplicate

## Problem

Given an integer array `nums`, return `true` if any value appears at least twice in the array. Return `false` if every element is distinct.

## Examples

```text
Input:  nums = [1, 2, 3, 1]
Output: true
Explanation: The value 1 appears more than once.
```

```text
Input:  nums = [1, 2, 3, 4]
Output: false
Explanation: Every value appears exactly once.
```

```text
Input:  nums = [1, 1, 1, 3, 3, 4, 3, 2, 4, 2]
Output: true
```

## Constraints

- `1 <= nums.length <= 10^5`
- `-10^9 <= nums[i] <= 10^9`

## Your task

1. Write a brute-force solution first.
2. State its time and space complexity.
3. Improve it using a `HashSet`.
4. Test it with the examples and at least two edge cases.

## Java method signature

```java
public boolean containsDuplicate(int[] nums) {
    HashSet<Integer> seen = new HashSet<>();

    for (int num : nums) {
        if (seen.contains(num)) {
            return true;
        }
        seen.add(num);
    }
    return false;
}
```

## Edge cases to test

- A single element: `[1]`
- Two identical values: `[5, 5]`
- Negative values: `[-1, -2, -3, -1]`
- All values are distinct: `[10, 20, 30]`

## Hint

Maintain a set of values encountered so far. Before adding each value, check whether it is already in the set.
