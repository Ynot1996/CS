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
[283](https://leetcode.com/problems/binary-tree-inorder-traversal/)

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

## Binary Tree Preorder Traversal
[144](https://leetcode.com/problems/binary-tree-preorder-traversal/)

## Binary Tree Postorder Traversal
[145](https://leetcode.com/problems/binary-tree-postorder-traversal/)




