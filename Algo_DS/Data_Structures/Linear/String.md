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
## 基礎字串操作
1. 字串方法
str.lower() / str.upper()：轉小寫 / 大寫。
str.strip()：移除頭尾空白或指定字符。
str.replace(old, new)：取代子字串。
str.split(separator)：拆分字串，預設用空白分隔。
str.join(iterable)：以字串連結可迭代對象。
str.find(sub) / str.index(sub)：查找子字串的索引（find 不存在時返回 -1，index 會報錯）。
str.count(sub)：計算子字串出現次數。
str.startswith(prefix) / str.endswith(suffix)：檢查是否以某子字串開頭或結尾。

2. 字串切片
string[start:end:step]：
取得指定範圍的子字串。
支援反向切片（step=-1）。

3. 格式化字串
舊式格式化："Hello, %s!" % name
新式格式化："Hello, {}!".format(name)
f-string：f"Hello, {name}!"（Python 3.6+）

## 進階字串操作
1. 正規表達式（Regular Expression） 使用 re 模組處理複雜字串匹配與替換：

```python
import re

result = re.search(r'\d+', 'Age: 25')
print(result.group())  # '25'

new_string = re.sub(r'\d+', '30', 'Age: 25')
print(new_string)  # 'Age: 30'
```

2. 字串翻轉
使用切片：reversed_string = string[::-1]

3. 字串檢查
字母或數字檢查：str.isalpha() / str.isdigit() / str.isalnum()
空白檢查：str.isspace()
大小寫檢查：str.islower() / str.isupper()

4. 處理多行字串
使用三重引號（''' 或 """）定義多行字串。
分割多行：str.splitlines()

5. 轉換為列表或字元

```python
char_list = list(string)  
new_string = ''.join(char_list)  
```

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Easy-->
## Reverse String
[344](https://leetcode.com/problems/reverse-string/)

Question: <br> 
Write a function that reverses a string. The input string is given as an array of characters s. <br>
You must do this by modifying the input array in-place with O(1) extra memory.

Example 1: <br>
Input: s = ["h","e","l","l","o"] <br>
Output: ["o","l","l","e","h"]

Example 2: <br>
Input: s = ["H","a","n","n","a","h"] <br>
Output: ["h","a","n","n","a","H"]

Method: Two Pointers

## Valid Anagram
[242](https://leetcode.com/problems/valid-anagram/)

Question: <br> 
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

Example 1: <br>
Input: s = "anagram", t = "nagaram" <br>
Output: true

Example 2: <br>
Input: s = "rat", t = "car" <br>
Output: false

Method 1: Hash Table <br>
Method 2: Sorting

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
[76](https://leetcode.com/problems/minimum-window-substring/)
## Regular Expression Matching
[10](https://leetcode.com/problems/regular-expression-matching/)
## Wildcard Matching
[44](https://leetcode.com/problems/wildcard-matching/)
## Longest Duplicate Substring
[1044](https://leetcode.com/problems/longest-duplicate-substring/)
## Palindrome Partitioning II
[132](https://leetcode.com/problems/palindrome-partitioning-II/)

