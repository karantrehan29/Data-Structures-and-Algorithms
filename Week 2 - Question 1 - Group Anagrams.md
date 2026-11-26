# Week 2 — Question 1: Group Anagrams

## Problem

Given an array of strings, group together the strings that contain the same letters with the same frequencies. You may return the groups in any order.

## Examples

```text
Input:  strs = ["eat", "tea", "tan", "ate", "nat", "bat"]
Output: [["eat", "tea", "ate"], ["tan", "nat"], ["bat"]]
```

```text
Input:  strs = [""]
Output: [[""]]
```

```text
Input:  strs = ["a"]
Output: [["a"]]
```

## Constraints

- `1 <= strs.length <= 10^4`
- `0 <= strs[i].length <= 100`
- `strs[i]` contains lowercase English letters.

## Your task

1. Implement the method below.
2. State its time and space complexity.
3. Test the examples and at least two additional edge cases.

## Java method signature

```java
public List<List<String>> groupAnagrams(String[] strs) {
    List<List<String>> groupedAnagrams = new ArrayList<>();
    Map<Map<Character, Integer>, List<String>> groups = new HashMap<>();

    for(String str: strs)
    {
        Map<Character,Integer> frequency = getFrequency(str);
        if(groups.containsKey(frequency))
        {
            List<String> group = groups.get(frequency);
            group.add(str);
            groups.put(frequency, group);
        } else {
            List<String> group = new ArrayList(List.of(str));
            groups.put(frequency, group);
        }
    }

    for(List<String> group: groups.values())
    {
        groupedAnagrams.add(group);
    }

    return groupedAnagrams;
}

public Map<Character, Integer> getFrequency(String str) {
    Map<Character, Integer> frequency = new HashMap<>();

    for(char c : str.toCharArray())
    {
        frequency.put(c, frequency.getOrDefault(c,0) + 1);
    }
    return frequency;
}
```
