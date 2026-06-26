# Day 1

## Problem 1- Pascal's Triangle

### LINK
https://leetcode.com/problems/pascals-triangle/

### DESCRIPTION AND UNDERSTANDING
A pascal triangle is a triangle where each number is the sum of the two directly above it. The input of this code will be the number of arrays and the output should present an array containing each row.

---

The pattern for generating each row is that each row is the sum of the two numbers above it i.e. new_row[j]=row[j-1]+row[j]
The corner edges will always be one. So, that value should always be appended before and after the middle value

### Code

```python
class Solution(object):
    def generate(self, numRows):
        triangle=[[1]]
        for i in range(numRows-1):
            row = triangle[-1]
            next_row=[]
            next_row.append(1)
            for j in range(1,len(row)):
                next_row.append(row[j-1]+row[j])
            next_row.append(1)
            triangle.append(next_row)
        return triangle
```

### Time Complexity
O(n²)

### What I Learned

- Building arrays from previous arrays
- Nested loops
- List indexing