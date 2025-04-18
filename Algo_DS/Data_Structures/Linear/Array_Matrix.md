# Array and Matrix

### Array
- [283. Move Zeroes (Easy)](#Move-Zeroes)
- [Degree of an Array (Easy)](#Degree-of-an-Array)
- [Max Consecutive Ones (Easy)](#Max-Consecutive-Ones)
- [Find the Duplicate Number (Medium)](#Find-the-Duplicate-Number)

### Matrix
- [832. Flipping an Image (Easy)](#Flipping-an-Image)
- [867. Transpose Matrix (Easy)](#Transpose-Matrix)
- [Search a 2D Matrix II (Medium)](#Search-a-2D-Matrix-II)
- [Kth Smallest Element in a Sorted Matrix (Medium)](#Kth-Smallest-Element-in-a-Sorted-Matrix)

<!--Array-->
## Move Zeroes
[283](https://leetcode.com/problems/move-zeroes/)

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

```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        zero_index = 0
        for i in range(len(nums)):
            if nums[i] != 0:  
                nums[i], nums[zero_index] = nums[zero_index], nums[i]  
                zero_index += 1
```

![image](https://github.com/user-attachments/assets/a2b7228c-ea45-4b20-94e9-041d16cad170)

## Degree of an Array
[697](https://leetcode.com/problems/degree-of-an-array/)

## Max Consecutive Ones
[485](https://leetcode.com/problems/max-consecutive-ones/)

## Find the Duplicate Number
[287](https://leetcode.com/problems/find-the-duplicate-number/)

<!--Matrix-->
## Flipping an Image
[832](https://leetcode.com/problems/Flipping-an-Image/)

```python
class Solution:
    def flipAndInvertImage(self, image: List[List[int]]) -> List[List[int]]:
        n = len(image)

        for i in range(n):
            image[i] = image[i][::-1]

            for j in range(n):
                image[i][j] = 1 - image[i][j]

        return image
```

Advanced Syntax
```python
class Solution:
    def flipAndInvertImage(self, image: List[List[int]]) -> List[List[int]]:
        return [[1 - i for i in row[::-1]] for row in image]
```

## Transpose Matrix
[867](https://leetcode.com/problems/Transpose-Matrix/)

```python
class Solution:
    def transpose(self, matrix: List[List[int]]) -> List[List[int]]:
        result = []

        for i in range(len(matrix[0])):
            new_row = []
            for j in range(len(matrix)):
                new_row.append(matrix[j][i])
            result.append(new_row)
        
        return result
```

## Search a 2D Matrix II
[240](https://leetcode.com/problems/search-a-2d-matrix-ii/)

## Kth Smallest Element in a Sorted Matrix
[378](https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix/)








