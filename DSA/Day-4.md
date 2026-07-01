# Contains Duplicate

## LINK
https://leetcode.com/problems/contains-duplicate/

## DESCRIPTION AND UNDERSTANDING
Given an integer array, return `true` if any value appears at least twice, and `false` if every element is distinct.

---

The simplest approach is to use a **set** — as we walk through the array, we check if the current number has already been seen. If yes, return `true` immediately. If we finish the whole array without finding a duplicate, return `false`.

A set is ideal here because:
- Checking if an element exists in a set is O(1)
- Sets only store unique values, so duplicates are naturally caught

### Code

```python
class Solution(object):
    def containsDuplicate(self, nums):
        seen = set()
        for num in nums:
            if num in seen:
                return True
            seen.add(num)
        return False
```

## Time Complexity
O(n) — single pass through the array, each set lookup and insert is O(1)

## Space Complexity
O(n) — the set stores at most n elements in the worst case (all distinct)

## What I Learned

- Using a set as a "memory" of what we've already seen — O(1) lookup vs O(n) for a list
- Early return pattern: return the answer the instant you find it, don't finish the loop unnecessarily
- Time vs space tradeoff: we spend O(n) space to get O(n) time (sorting would be O(1) space but O(n log n) time)