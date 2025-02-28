# Heap
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [703. Kth Largest Element in a Stream](#Kth-Largest-Element-in-a-Stream)

### Medium
- [215. Kth Largest Element in an Array](#Kth-Largest-Element-in-an-Array)
- [237. K Closest Points to Origin](#K-Closest-Points-to-Origin)
- [378. Kth Smallest Element in a Sorted Matrix](#Kth-Smallest-Element-in-a-Sorted-Matrix)

### Hard
- [23. Merge k Sorted Lists](#Merge-k-Sorted-Lists)
- [298. Find Median from Data Stream](#Find-Median-from-Data-Stream)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Easy-->
## Kth Largest Element in a Stream
[703](https://leetcode.com/problems/Kth-Largest-Element-in-a-Stream/)
```python
class KthLargest:

    def __init__(self, k: int, nums: List[int]):
        self.minHeap, self.k = nums, k
        heapq.heapify(self.minHeap)
        while len(self.minHeap) > k:
            heapq.heappop(self.minHeap)

    def add(self, val: int) -> int:
        heapq.heappush(self.minHeap, val)
        if len(self.minHeap) > self.k:
            heapq.heappop(self.minHeap)
        return self.minHeap[0]
```
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Medium-->
## K Closest Points to Origin
[237](https://leetcode.com/problems/K-Closest-Points-to-Origin/)

## Kth Largest Element in an Array
[215](https://leetcode.com/problems/Kth-Largest-Element-in-an-Array/)

## Kth Smallest Element in a Sorted Matrix
[378](https://leetcode.com/problems/Kth-Smallest-Element-in-a-Sorted-Matrix/)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Hard-->
## Merge K Sorted Lists
[23](https://leetcode.com/problems/Merge-K-Sorted-Lists/)

## Find Median from Data Stream
[298](https://leetcode.com/problems/Find-Median-from-Data-Stream/)
