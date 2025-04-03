# Binary_Search
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy

### Medium
- [2300. Successful Pairs of Spells and Potions](#Successful-Pairs-of-Spells-and-Potions)

### Hard

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
## Successful Pairs of Spells and Potions
[2300](https://leetcode.com/problems/Successful-Pairs-of-Spells-and-Potions/)

You are given two positive integer arrays spells and potions, of length n and m respectively, where spells[i] represents the strength of the ith spell and potions[j] represents the strength of the jth potion.

You are also given an integer success. A spell and potion pair is considered successful if the product of their strengths is at least success.

Return an integer array pairs of length n where pairs[i] is the number of potions that will form a successful pair with the ith spell.

Method 1: Brute Force
>>> Time Limit Exceeded
```python
class Solution:
    def successfulPairs(self, spells: List[int], potions: List[int], success: int) -> List[int]:
        res = [0] * len(spells)
        for n in range(len(spells)):
            for m in potions:
                if spells[n]*m >= success:
                    res[n] += 1
        return res
```
Method 2: Binary Search 
