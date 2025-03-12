# Graph
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Graph Traversal: DFS & BFS
- [200. Number of Islands (Medium)](#Number-of-Islands)
- [695. Max Area of Island (Medium)](#Max-Area-of-Island)
  
### Topological Sorting
- [207. Course Schedule (Medium)](#Course-Schedule)
- [210. Course Schedule II (Medium)](#Course-Schedule-II)

### Shortest Path
- [743. Network Delay Time (Medium)](#Network-Delay-Time)
- [787. Cheapest Flights Within K Stops (Medium)](#Cheapest-Flights-Within-K-Stops)

### Connected Components
- [547. Number of Provinces (Medium)](#Number-of-Provinces)
- [684. Redundant Connection (Medium)](#Redundant-Connection)

### MST
- [1135. Connecting Cities With Minimum Cost (Medium)](#Connecting-Cities-With-Minimum-Cost)
- [1584. Min Cost to Connect All Points (Medium)](#Min-Cost-to-Connect-All-Points)


### Bipartite Graph
- [785. Is Graph Bipartite? (Medium)](#Is-Graph-Bipartite?)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
## Number of Islands
[200](https://leetcode.com/problems/Number-of-Islands/)
```python
class Solution:
    def numIslands(self, grid: List[List[str]]) -> int:
        if not grid:
            return 0
        
        rows, cols = len(grid), len(grid[0])
        visit = set()
        islands = 0

        def bfs(r,c):
            q = collections.deque()
            visit.add((r, c))
            q.append((r, c))
            while q:
                row, col = q.popleft()
                directions = [[1, 0], [-1, 0], [0, 1], [0, -1]]
                for dr, dc in directions:
                    r, c = row + dr, col + dc
                    if (r in range(rows) and c in range(cols) and grid[r][c] == "1" and (r, c) not in visit):
                        q.append((r, c))
                        visit.add((r, c))
                        
        for r in range(rows):
            for c in range(cols):
                if grid[r][c] == "1" and (r, c) not in visit:
                    bfs(r, c)
                    islands += 1
        return islands
```
