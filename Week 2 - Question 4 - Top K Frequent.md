# Week 2 — Question 4: Top K Frequent Elements

## Problem

Given an integer array `nums` and an integer `k`, return the `k` values that occur most frequently. The result may be returned in any order.

## Examples

```text
Input:  nums = [1, 1, 1, 2, 2, 3], k = 2
Output: [1, 2]
```

```text
Input:  nums = [1], k = 1
Output: [1]
```

## Constraints

- `1 <= nums.length <= 10^5`
- `-10^4 <= nums[i] <= 10^4`
- `k` is between `1` and the number of distinct values in `nums`.
- The answer is unique.

## Your task

1. Implement the method below.
2. Analyze its time and space complexity.
3. Test the examples and at least two additional edge cases.

## Java method signature

```java
public int[] topKFrequent(int[] nums, int k) {

    int[] result = new int[k];
    PriorityQueue<Map.Entry<Integer, Integer>> queue = new PriorityQueue<>((q1,q2) -> Integer.compare(q2.getValue(), q1.getValue()));
    Map<Integer, Integer> frequency = new HashMap<>();

    for(int num: nums)
    {
        frequency.put(num, frequency.getOrDefault(num,0) + 1);
    }

    for(Map.Entry<Integer, Integer> entry: frequency.entrySet())
    {
        queue.offer(entry);
    }

    for(int i=0; i<k; i++)
    {
        result[i] = queue.poll().getKey();
    }

    return result;
}
```
