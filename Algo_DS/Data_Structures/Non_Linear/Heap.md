# Heap
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [703. Kth Largest Element in a Stream](#Kth-Largest-Element-in-a-Stream)
- [1046. Last Stone Weight](#Last-Stone-Weight)
  
### Medium
- [215. Kth Largest Element in an Array](#Kth-Largest-Element-in-an-Array)
- [378. Kth Smallest Element in a Sorted Matrix](#Kth-Smallest-Element-in-a-Sorted-Matrix)
- [973. K Closest Points to Origin](#K-Closest-Points-to-Origin)


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

## Last Stone Weight
[1046](https://leetcode.com/problems/Last-Stone-Weight/)

We are playing a game with the stones. On each turn, we choose the heaviest two stones and smash them together. Suppose the heaviest two stones have weights x and y with x <= y. The result of this smash is:

- If x == y, both stones are destroyed, and
- If x != y, the stone of weight x is destroyed, and the stone of weight y has new weight y - x.
At the end of the game, there is at most one stone left.

Return the weight of the last remaining stone. If there are no stones left, return 0.

```java
class Solution {
    public int lastStoneWeight(int[] stones) {
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        for (int stone : stones) {
            maxHeap.add(stone);
        }
        while (maxHeap.size() > 1) {
            int stone1 = maxHeap.poll();
            int stone2 = maxHeap.poll();
            if (stone1 != stone2) {
                maxHeap.add(stone1 - stone2);
            }
        }
        return maxHeap.isEmpty() ? 0 : maxHeap.poll();
    }
}
```

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Medium-->
## Kth Largest Element in an Array
[215](https://leetcode.com/problems/Kth-Largest-Element-in-an-Array/)

```java
class Solution {
    public int findKthLargest(int[] nums, int k) {
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        for (int num : nums) {
            maxHeap.add(num);
        }
        for (int i = 1; i < k; i++) {
            maxHeap.poll();
        }
        return maxHeap.peek();
    }
}
```

## Kth Smallest Element in a Sorted Matrix
[378](https://leetcode.com/problems/Kth-Smallest-Element-in-a-Sorted-Matrix/)

## K Closest Points to Origin
[973](https://leetcode.com/problems/K-Closest-Points-to-Origin/)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Hard-->
## Merge K Sorted Lists
[23](https://leetcode.com/problems/Merge-K-Sorted-Lists/)

## Find Median from Data Stream
[298](https://leetcode.com/problems/Find-Median-from-Data-Stream/)
