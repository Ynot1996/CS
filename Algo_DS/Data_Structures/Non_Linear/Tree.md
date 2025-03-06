# Tree

### Tree Traversal 
DFS
- [94. Binary Tree Inorder Traversal (Easy)](#Binary-Tree-Inorder-Traversal)
- [144. Binary Tree Preorder Traversal (Easy)](#Binary-Tree-Preorder-Traversal)
- [145. Binary Tree Postorder Traversal (Easy)](#Binary-Tree-Postorder-Traversal)
- [105. Construct Binary Tree from Preorder and Inorder Traversal (Medium)](#Construct-Binary-Tree-from-Preorder-and-Inorder-Traversal) 

BFS
- [102. Binary Tree Level Order Traversal (Medium)](#Binary-Tree-Level-Order-Traversal)
- [103. Binary Tree Zigzag Level Order Traversal (Medium)](#Binary-Tree-Zigzag-Level-Order-Traversal)
- [107. Binary Tree Level Order Traversal II (Medium)](#Binary-Tree-Level-Order-Traversal-II)

### Trie

## Binary Tree Inorder Traversal
[94](https://leetcode.com/problems/Binary-Tree-Inorder-Traversal/)
```python
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        result = []
        def inorder(node):
            if not node:
                return
            inorder(node.left)
            result.append(node.val)
            inorder(node.right)
        inorder(root)
        return result
```

## Binary Tree Preorder Traversal
[144](https://leetcode.com/problems/Binary-Tree-Preorder-Traversal/)
```python
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        result = []
        def inorder(node):
            if not node:
                return
            result.append(node.val)
            inorder(node.left)
            inorder(node.right)
        inorder(root)
        return result
```
## Binary Tree Postorder Traversal
[145](https://leetcode.com/problems/Binary-Tree-Postorder-Traversal/)
```python
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        result = []
        def inorder(node):
            if not node:
                return
            inorder(node.left)
            inorder(node.right)
            result.append(node.val)
        inorder(root)
        return result
```
