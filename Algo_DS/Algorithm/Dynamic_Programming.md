# Dynamic Programming
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [118. Pascal's Triangle](#Pascals-Triangle)
  
### Medium
- [62. Unique Paths](#Unique-Paths)
- [198. House Robber](#House-Robber)
- [322. Coin Change](#Coin-Change)
  
### Hard


<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Easy-->
## Pascal's Triangle
[118](https://leetcode.com/problems/Pascals-Triangle/)

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

## House Robber
[198](https://leetcode.com/problems/House-Robber/)

```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        n = len(nums)
        if n == 1:
            return nums[0]
        
        dp = [0] * n
        dp[0] = nums[0]
        dp[1] = max(dp[0], nums[1])

        for i in range(2, n):
            dp[i] = max(dp[i-1], dp[i-2] + nums[i])

        return dp[-1]
```

## Coin Change
[322](https://leetcode.com/problems/Coin-Change/)

NeetCode: https://youtu.be/H9bfqozjoqs?si=Xefvb38J6dvixyFF

Beautiful Solution
```python
class Solution:
    def coinChange(self, coins: List[int], amount: int) -> int:
        dp = [amount + 1] * (amount + 1)
        dp[0] = 0
        
        for a in range(1, amount + 1):
            for c in coins:
                if a - c >= 0:
                    dp[a] = min(dp[a], 1 + dp[a - c])
        
        return dp[amount] if dp[amount] != amount + 1 else -1
```
