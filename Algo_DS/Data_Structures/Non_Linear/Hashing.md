# Hashing
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
These problems focus on fundamental HashSet / HashMap usage, such as checking duplicates, counting frequencies, and finding value mappings.
- [1. Two Sum](#Two-Sum)
- [217. Contains Duplicate](#Contains-Duplicate)
- [242. Valid Anagram](#Valid-Anagram)
- [349. Intersection of Two Arrays](#Intersection-of-Two-Arrays)

### Medium
These problems involve HashMap for solving more complex problems like substring matching, prefix sums, and sliding window techniques.
- [3. Kth Largest Element in an Array](#Kth-Largest-Element-in-an-Array)
- [451. Sort Characters By Frequency](#Sort-Characters-By-Frequency)
- [525. Contiguous Array](#Contiguous-Array)
- [560. Subarray Sum Equals K](#Subarray-Sum-Equals-K)

### Hard
These problems combine hashing with other structures like heaps, linked lists, trees, and bit manipulation, which are commonly asked in interviews.
- [30. Substring with Concatenation of All Words](#Substring-with-Concatenation-of-All-Words)
- [76. Minimum Window Substring](#Minimum-Window-Substring)
- [128. Longest Consecutive Sequence](#Longest-Consecutive-Sequence)
- [146. LRU Cache](#LRU-Cache)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Easy-->
## Two Sum
[1](https://leetcode.com/problems/Two-Sum/)

Using HashMap to store indices for O(N) solution
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {

            if (map.containsKey(target-nums[i])){
                return new int[]{map.get(target - nums[i]), i};
            } 

            map.put(nums[i], i);
        }
        return new int[0];
    }
}
```
## Contains Duplicate
[217](https://leetcode.com/problems/Contains-Duplicate/)

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        a = set()
        for i in nums:
            if i in a:
                return True
            
            a.add(i)
        return False
```
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Medium-->

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Hard-->


