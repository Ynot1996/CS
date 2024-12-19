# String
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [Reverse String](#Reverse-String)
- [Valid Anagram](#Valid-Anagram)
- [Implement strStr()](#Implement-strStr())

### Medium
- [Longest Substring Without Repeating Characters](#Longest-Substring-Without-Repeating-Characters)
- [Longest Palindromic Substring](#Longest-Palindromic-Substring)
- [Group Anagrams](#Group-Anagrams)
- [Add Strings](#Add-Strings)
- [Group Anagrams](#Group-Anagrams)
- [Longest Common Prefix](#Longest-Common-Prefix)
- [Decode String](#Decode-String)
- [String to Integer (atoi)](#String-to-Integer-(atoi))

### Medium
- [Minimum Window Substring](#Minimum-Window-Substring)
- [Regular Expression Matching](#Regular-Expression-Matching)
- [Wildcard Matching](#Wildcard-Matching)
- [Longest Duplicate Substring](#Longest-Duplicate-Substring)
- [Palindrome Partitioning II](#Palindrome-Partitioning-II)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Easy-->
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

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Medium-->
## Longest Substring Without Repeating Characters
[3](https://leetcode.com/problems/longesr-substring-without-repeating-characters/)
## Longest Palindromic Substring
[5](https://leetcode.com/problems/longest-palindromic-substring/)
## Group Anagrams
[49](https://leetcode.com/problems/group-anagrams/)
## Add Strings
[415](https://leetcode.com/problems/add-strings/)
## Longest Common Prefix
[14](https://leetcode.com/problems/longest-common-prefix/)
## Decode String
[394](https://leetcode.com/problems/decode-string/)
## String to Integer (atoi)
[8](https://leetcode.com/problems/string-to-integer-(atoi)/)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Hard-->
## Minimum Window Substring
[76](https://leetcode.com/problems/valid-anagram/)
## Regular Expression Matching
[10](https://leetcode.com/problems/regular-expression-matching/)
## Wildcard Matching
[44](https://leetcode.com/problems/wildcard-matching/)
## Longest Duplicate Substring
[1044](https://leetcode.com/problems/longest-duplicate-substring/)
## Palindrome Partitioning II
[132](https://leetcode.com/problems/palindrome-partitioning-II/)

