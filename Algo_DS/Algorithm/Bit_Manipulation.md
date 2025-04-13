# Bit Manipulation
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [136. Single Number](#Single-Number)
- [191. Number of 1 Bits](#Number-of-1-Bits)
- [338. Counting Bits](#Counting-Bits)
  
### Medium
- [](#)
- [](#)

### Hard

## Single Number
[136](https://leetcode.com/problems/Single-Number/)

```python

```

## Number of 1 Bits
[191](https://leetcode.com/problems/Number-of-1-Bits/)

Method: Math 
```python
class Solution:
    def hammingWeight(self, n: int) -> int:
        count = 0
        while n > 0:
            if n % 2 != 0:
                count += 1
            n = n // 2
        return count 
```

Method: Bit Manipulation
```python
class Solution:
    def hammingWeight(self, n: int) -> int:
        count = 0
        while n:
            count += n & 1
            n >>= 1
        return count 
```

## Counting Bits
[338](https://leetcode.com/problems/Counting-Bits/)

Method 1: O(n log n), by hammingWeight
```python
class Solution:
    def countBits(self, n: int) -> List[int]:

        def hammingWeight(number):
            count = 0
            while number:
                count += number & 1
                number >>= 1
            return count

        ans = []
        for i in range(n+1):
            ans.append(hammingWeight(i))
        return ans
```

Method 2: O(n), by DP
```python
class Solution:
    def countBits(self, n: int) -> List[int]:
        dp = [0] * (n + 1)
        for i in range(1, n + 1):
            dp[i] = dp[i >> 1] + (i & 1)
        return dp
```

![image](https://github.com/user-attachments/assets/0b64cf30-18b7-4bbd-ba5b-5744ac820a25)
