# Stack and Queue

### Stack
- [Binary Tree Inorder Traversal (Easy)](#Binary-Tree-Inorder-Traversal)
- [Binary Tree Preorder Traversal (Easy)](#Binary-Tree-Preorder-Traversal)
- [Binary Tree Postorder Traversal (Easy)](#Binary-Tree-Postorder-Traversal)

### Queue
- [](#)
- [](#)

<!--Array-->
## Binary Tree Inorder Traversal
[283]([https://leetcode.com/problems/move-zeroes/])

Question: <br> 
Given the root of a binary tree, return the inorder traversal of its nodes' values.

Method: Stack<br>

```java
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        Stack<TreeNode> stack = new Stack<>();
        TreeNode curr = root;

        while (curr != null || !stack.isEmpty()) {
            while (curr != null) {
                stack.push(curr);
                curr = curr.left;
            }
            curr = stack.pop();
            result.add(curr.val);
            curr = curr.right;
        }

        return result;
    }
}
```

![image](https://github.com/user-attachments/assets/a2b7228c-ea45-4b20-94e9-041d16cad170)

## Degree of an Array
[697](https://leetcode.com/problems/degree-of-an-array/)

## Max Consecutive Ones
[485](https://leetcode.com/problems/max-consecutive-ones/)

## Find the Duplicate Number
[287](https://leetcode.com/problems/find-the-duplicate-number/)

<!--Matrix-->
## Search a 2D Matrix II
[240](https://leetcode.com/problems/search-a-2d-matrix-ii/)

## Kth Smallest Element in a Sorted Matrix
[378](https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix/)
