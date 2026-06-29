# Day 3

## Problem 1 - Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

### LINK

https://leetcode.com/problems/single-number/

### DESCRIPTION AND UNDERSTANDING

We do not use the obvious hash map method. A hashmap that counts occurrences works in O(n) time, but uses O(n) space, since the map grows with the input. The trick is to use XOR.
XOR has two properties that solve this perfectly:
- x ^ x = 0    (a number XORed with itself cancels out)
- x ^ 0 = x    (a number XORed with 0 is unchanged)
Since XOR is also commutative/associative (order doesn't matter), XORing every element in the array together causes every pair to cancel itself out to 0. Only the number that appears once has no partner to cancel with, so it's the only thing left standing at the end.

### Code

```python
class Solution(object):
    def singleNumber(self, nums):
        result = 0
        for num in nums:
            result = result ^ num
        return result
```
