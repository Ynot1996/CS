# Greedy 
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [122. Best Time to Buy and Sell Stock II](#Best-Time-to-Buy-and-Sell-Stock-II)
- [409. Longest Palindrome](#Longest-Palindrome)
- [455. Assign Cookies](#Assign-Cookies)
### Medium
- [55. Jump Game](#Jump-Game)
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

Even counts can always form symmetric pairs in a palindrome. (e.g., 2×'a' → "aa")

Odd counts can still contribute: use count - 1 to make pairs, and at most one odd character can be placed in the center.

Example:
For "aabbc", counts = {a:2, b:2, c:1}
→ Use 2+2 as pairs, and keep 'c' in the center → Result: "abcba" (length = 5)

```python
class Solution:
    def longestPalindrome(self, s: str) -> int:
        total = 0
        checkodd = False

        for i in Counter(s).values():
            if i % 2 == 0:
                total += i
            else:
                checkodd = True
                total += (i - 1)
        
        return total + 1 if checkodd else total
```

## Jump Game
[55](https://leetcode.com/problems/Jump-Game/)

```python
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        goal = len(nums) - 1
        for i in range(len(nums) - 2, -1, -1):
            if i + nums[i] >= goal:
                goal = i
        
        return True if goal == 0 else False
```
