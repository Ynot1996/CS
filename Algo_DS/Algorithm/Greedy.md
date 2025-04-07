# Greedy 
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [122. Best Time to Buy and Sell Stock II](#Best-Time-to-Buy-and-Sell-Stock-II)
- [409. Longest Palindrome](#Longest-Palindrome)
- [455. Assign Cookies](#Assign-Cookies)
### Medium
- [134. Gas Station](#Gas-Station)
- [406. Queue Reconstruction by Height](#Queue-Reconstruction-by-Height)
- [435. Non-overlapping intervals](#Non-overlapping-Intervals)
  
### Hard
- [763. Partition Lables](#Partition-Labels)
- [871. Minimum Number of Refueling Stops](#Minimum-Number-of-Refueling-Stops)
  
<!------------------------------------------------------------------------------------------------------------------------------------------------------>

## Best Time to Buy and Sell Stock II
[122](https://leetcode.com/problems/Best-Time-to-Buy-and-Sell-Stock-II/)

## Longest Palindrome
[409](https://leetcode.com/problems/Longest-Palindrome/)

```python
class Solution:
    def longestPalindrome(self, s: str) -> int:
        
        total = 0
        checkodd = False

        for i in Counter(s).values():
            if i % 2 == 0: 
                total += i
            elif i % 2 == 1:
                checkodd = True
                if i > 1:
                    total += (i - 1) 
        
        if checkodd:
            return total + 1
        
        else:
            return total
```
