# Week 2 — Question 2: Valid Anagram

## Problem

Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`;
otherwise, return `false`.

An anagram contains the same characters with the same frequencies, but the
characters may appear in a different order.

## Examples

```text
Input:  s = "listen", t = "silent"
Output: true
```

```text
Input:  s = "hello", t = "world"
Output: false
```

```text
Input:  s = "a", t = "aa"
Output: false
```

## Constraints

- `1 <= s.length, t.length <= 5 * 10^4`
- `s` and `t` contain lowercase English letters.

## Your task

1. Implement `boolean isAnagram(String s, String t)` in Java.
2. Analyze the time and space complexity of your approach.
3. Test the examples and at least two additional edge cases.

## Java method signature

```java
public boolean isAnagram(String s, String t) {

    if (s.length() != t.length()) {
        return false;
    }

    int[] frequency = new int[26];
    int n = s.length();

    for(int i=0; i<n; i++)
    {
        char c = s.charAt(i);
        frequency[c - 'a']++;
    }

    for(int i=0; i<n; i++)
    {
        char c = t.charAt(i);
        frequency[c - 'a']--;
    }

    for(int freq: frequency)
    {
        if(freq != 0) return false;
    }
    return true;
}
```
