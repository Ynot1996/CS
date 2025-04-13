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

```python

```
