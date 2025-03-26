# Linked List
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Medium
- [62. Unique Paths](#Unique-Paths)


### Hard


<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Easy-->
## Unique Paths
[62](https://leetcode.com/problems/Unique-Paths/)
![image](https://github.com/user-attachments/assets/8819c630-f086-4598-b86a-86fd0dde6df1)

```python
class Solution:
    def uniquePaths(self, m: int, n: int) -> int:
        row = [1] * n # bottom line
        
        for i in range(m - 1): # num of remaining rows is "m - 1" 
            newRow = [1] * n  # initialize the current row
            for j in range(n - 2, -1, -1): # iterate from the second last cell (right to left)
                newRow[j] = newRow[j + 1] + row[j] # current cell = right cell + bottom cell
            row = newRow # update row as the new bottom row for the next iteration 
        
        return row[0] # top-left corner
```

