# Week 1 — Question 3: Longest Substring Without Repeating Characters

## Problem

Given a string `s`, find the length of its longest contiguous substring that contains no repeated characters. Return `0` if `s` is empty.

## Examples

```text
Input:  s = "abcabcbb"
Output: 3
Explanation: "abc" is a longest substring with no repeated characters.
```

```text
Input:  s = "bbbbb"
Output: 1
```

```text
Input:  s = "pwwkew"
Output: 3
Explanation: "wke" is a valid substring. "pwke" is not contiguous.
```

## Constraints

- `0 <= s.length <= 5 * 10^4`
- `s` may contain letters, digits, symbols, and spaces.

## Your task

1. Implement the method below.
2. State its time and space complexity.
3. Test it with the examples and at least two additional edge cases.

## Java method signature

```java
public int lengthOfLongestSubstring(String s) {
    // Code here
    Map<Character, Integer> lastSeen = new HashMap<>();
    
    int left = 0;
    int right = 0;
    int longestLength = 0;

    for(char c : s.toCharArray())
    {
        if(lastSeen.containsKey(c))
        {
            left = Math.max(left, lastSeen.get(c) + 1);
        }
        longestLength = Math.max(longestLength, right - left + 1);
        lastSeen.put(c,right);
        right++;
    }
    return longestLength;
}
```
