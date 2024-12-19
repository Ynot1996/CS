# String

### Easy
- [Reverse String](#Reverse-String)
- [Valid Anagram](#Valid-Anagram)
- [Implement strStr()](#Implement-strStr())

### Medium
- [Find the Duplicate Number (Medium)](#Find-the-Duplicate-Number)
- [Search a 2D Matrix II (Medium)](#Search-a-2D-Matrix-II)
- [Kth Smallest Element in a Sorted Matrix (Medium)](#Kth-Smallest-Element-in-a-Sorted-Matrix)

## Reverse String
[344](https://leetcode.com/problems/reverse-string/)

Question: <br> 
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements. <br>
Note that you must do this in-place without making a copy of the array.

Example 1:<br>
Input: nums = [0,1,0,3,12] <br>
Output: [1,3,12,0,0]

Example 2: <br>
Input: nums = [0] <br>
Output: [0]

Method: Two Pointers<br>
One pointer starts at nums[0] (first pointer), while the other pointer traverses through the entire nums array. <br>
Whenever the second pointer points to a non-zero value, swap the values at the first pointer's position and the second pointer's position. <br>
Then, move the first pointer one step forward and continue traversing the array until it is finished. 
## Valid Anagram
[242](https://leetcode.com/problems/valid-anagram/)
## Implement strStr()
[28](https://leetcode.com/problems/implement-strStr()/)
