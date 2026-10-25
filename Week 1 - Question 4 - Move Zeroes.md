# Week 1 — Question 4: Move Zeroes

## Problem

Given an integer array `nums`, move every `0` to the end of the array in
place. Keep the relative order of all non-zero values unchanged.

Do not create another array. The number of zeroes in the array must remain
unchanged.

## Examples

```text
Input:  nums = [0, 1, 0, 3, 12]
Output: [1, 3, 12, 0, 0]
```

```text
Input:  nums = [4, 0, 5]
Output: [4, 5, 0]
```

```text
Input:  nums = [0, 0, 0]
Output: [0, 0, 0]
```

## Constraints

- `1 <= nums.length <= 10^5`
- `-10^9 <= nums[i] <= 10^9`

## Your task

1. Describe a straightforward approach and analyze its time and space
   complexity.
2. Implement an in-place solution that uses O(1) extra space.
3. Preserve the relative order of non-zero values.
4. Test the examples and at least two additional edge cases.

## Java method signature

```java
public void moveZerosToEnd(int[] nums) {
    int leftPointer = 0;
    int rightPointer = 0;

    for(int num: nums)
    {
        if(num !=0)
        {
            int temp = nums[leftPointer];
            nums[leftPointer] = nums[rightPointer];
            nums[rightPointer] = temp;
            leftPointer++;
        }
        rightPointer++;
    }
}
```

## Edge cases to test

- No zeroes: `[1, 2, 3]`
- Zeroes at the beginning: `[0, 0, 1, 2]`
- Zeroes at the end: `[1, 2, 0, 0]`
- Negative and positive non-zero values: `[-1, 0, 2, 0, -3]`

## Hint

Consider using two indices: one to scan the array and one to track where the
next non-zero value should go.
