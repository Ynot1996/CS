# Sorting
<!-- GFM-TOC -->
* [Fundamental Sorting Concepts](#Fundamental-Sorting-Concepts)
    * [Bubble Sort](#Bubble-Sort)
      * [88. Merge Sorted Array (Easy)](#88-Merge-Sorted-Array)
    * [Selection Sort](#Selection-Sort)
        * [215. Kth Largest Element in an Array (Medium)](#215-Kth-Largest-Element-in-an-Array---Selection-Sort)
    * [Insertion Sort](#Insertion-Sort)
        * [147. Insertion Sort List (Medium)](#147-Insertion-Sort-List)   
         
* [Efficient Sorting Algorithms](#Efficient-Sorting-Algorithms)
    * [Merge Sort](#Merge-Sort)
      * [21. Merge Two Sorted Lists (Easy)](#21-Merge-Two-Sorted-Lists)
    * [Quick Sort](#Quick-Sort)
        * [75. Sort Colors (Medium)](#75-Sort-Colors)
    * [Heap Sort](#Heap-Sort)
        * [215. Kth Largest Element in an Array (Medium)](#215-Kth-Largest-Element-in-an-Array---Heap-Sort)
     
* [Advanced Sorting Algorithms](#Advanced-Sorting-Algorithms)
    * [Counting Sort](#Counting-Sort)
      * [912. Sort an Array (Medium)](#912-Sort-an-Array)
    * [Radix Sort](#Radix-Sort)
        * [164. Maximum Gap (Medium)](#164-Maximum-Gap)
    * [Bucket Sort](#Bucket-Sort)
        * [347. Top K Frequent Elements (Medium)](#347-Top-K-Frequent-Elements)   

# Fundamental Sorting Concepts

## Bubble Sort

Repeatedly swaps adjacent elements if they are in the wrong order.

#### 88. Merge Sorted Array

[Leetcode](https://leetcode.com/problems/merge-sorted-array/description/)

## Selection Sort

Selects the smallest (or largest) element from the unsorted portion and swaps it with the first unsorted element.

#### 215. Kth Largest Element in an Array - Selection Sort

[Leetcode](https://leetcode.com/problems/kth-largest-element-in-an-array/description/)

## Insertion Sort

Builds the sorted array one element at a time by inserting elements into their correct position.

#### 147. Insertion Sort List

[Leetcode](https://leetcode.com/problems/insertion-sort-list/description/)

# Efficient Sorting Algorithms

## Merge Sort

Divide-and-conquer strategy that splits the array in half, recursively sorts them, and merges them back together.

#### 21. Merge Two Sorted Lists

[Leetcode](https://leetcode.com/problems/merge-two-sorted-lists/description/)

## Quick Sort

Choose a pivot, partition the array around the pivot, and recursively sort the subarrays.

#### 75. Sort Colors

[Leetcode](https://leetcode.com/problems/sort-colors/description/)

## Heap Sort

Builds a heap (max or min) and repeatedly extracts the largest (or smallest) element.

#### 215. Kth Largest Element in an Array - Heap Sort

[Leetcode](https://leetcode.com/problems/kth-largest-element-in-an-array/description/)

# Advanced Sorting Algorithms

## Counting Sort

Sorts integers by counting the frequency of each value and uses this to place them in the correct position.

#### 912. Sort an Array

[Leetcode](https://leetcode.com/problems/sort-an-array/description/)

## Radix Sort

Sorts numbers by processing digits from least significant to most significant.

#### 164. Maximum Gap

[Leetcode](https://leetcode.com/problems/maximum-gap/description/)

## Bucket Sort

Divides the input into several "buckets," sorts each bucket, and combines the results.

#### 347. Top K Frequent Elements

[Leetcode](https://leetcode.com/problems/Top-K-Frequent-Elements/description/)

```python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        count = {}
        freq = [[] for i in range(len(nums) + 1)]

        for n in nums:
            count[n] = 1 + count.get(n, 0)
        for n, c in count.items():
            freq[c].append(n)
        
        res = []
        for i in range(len(freq) - 1, 0, -1):
            for n in freq[i]:
                res.append(n)
                if len(res) == k:
                    return res
```
