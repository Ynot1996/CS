# Dynamic Programming
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [118. Pascal's Triangle](#Pascal's-Triangle)
  
### Medium
- [62. Unique Paths](#Unique-Paths)

### Hard


<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Easy-->
## Pascal's Triangle
[118](https://leetcode.com/problems/Pascal's-Triangle/)

```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        triangle = []
        for i in range(numRows):
            row = [1] * (i+1)
            for j in range(1 , i):
                row[j] = triangle[i-1][j-1] + triangle[i-1][j]
            triangle.append(row)
        return triangle
```

<!--Meidum-->
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

