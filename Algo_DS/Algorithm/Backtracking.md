# Backtracking

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy

### Medium
- [17. Letter Combinations of a Phone Number](#Letter-Combinations-of-a-Phone-Number)
- [79. Word Search](#Word-Search)
- [216. Combination Sum III](#Combination-Sum-III)
  
### Hard
- [212. Word Search II](#Word-Search-II)
    
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
## Letter Combinations of a Phone Number
[17](https://leetcode.com/problems/Letter-Combinations-of-a-Phone-Number/)

## Word Search
[79](https://leetcode.com/problems/Word-Search/)

NeetCode: https://youtu.be/pfiQ_PS1g8E?si=OOXJcUn_mKAJfG2v
```python
class Solution:
    def exist(self, board: List[List[str]], word: str) -> bool:
        rows, cols = len(board), len(board[0])
        path = set()

        def dfs(r, c, i):
            if i == len(word):
                return True
            if ((r < 0 or c < 0) or (r >= rows or c >= cols) or (word[i] !=  board[r][c]) or ((r,c) in path)):
                return False
            path.add((r, c))
            res = dfs(r+1, c, i+1) or dfs(r-1, c, i+1) or dfs(r, c+1, i+1) or dfs(r, c-1, i+1)
            path.remove((r,c))
            return res

        for r in range(rows):
            for c in range(cols):
                if dfs(r, c, 0): return True
        return False
```

## Combination Sum III
[216](https://leetcode.com/problems/Combination-Sum-III/)

```python

```

## Word Search II
[212](https://leetcode.com/problems/Word-Search-II/)

Before starting this question, it's important to understand the concepts of prefix tree (Trie) and basic backtracking.

Prerequisites:

79. Word Search – introduces backtracking on a grid

208. Implement Trie (Prefix Tree) – covers Trie data structure

This problem is essentially a combination of the techniques from the two problems above. Understanding both is crucial to solving it efficiently.

```python

```
