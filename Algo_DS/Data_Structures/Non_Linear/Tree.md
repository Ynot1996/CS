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

### BST
- [700. Search in a Binary Search Tree (Easy)](#Search-in-a-Binary-Search-Tree)
  
### Trie
- [208. Implement Trie (Medium)](#Implement-Trie)
  
<!--Tree Traversal>
<!---------------------------------------------------------------------------------------------->
## Tree Traversal

### Binary Tree Inorder Traversal
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

### Binary Tree Preorder Traversal
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
### Binary Tree Postorder Traversal
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

<!--BST>
<!---------------------------------------------------------------------------------------------->
## BST

### Search in a Binary Search Tree
[700](https://leetcode.com/problems/Search-in-a-Binary-Search-Tree/)
- Recursive
```python
class Solution:
    def searchBST(self, root: TreeNode, val: int) -> TreeNode:
        if not root:
            return None
        if root.val == val:
            return root
        elif val < root.val:
            return self.searchBST(root.left, val)
        else:
            return self.searchBST(root.right, val)
```
- Iterative
```python
class Solution:
    def searchBST(self, root: Optional[TreeNode], val: int) -> Optional[TreeNode]:
        while root:
            if root.val == val:
                return root
            elif val < root.val:
                root = root.left
            else:
                root = root.right
        return None
```

<!--Trie>
<!---------------------------------------------------------------------------------------------->
## Trie

### Implement Trie 
[208](https://leetcode.com/problems/Implement-Trie-Prefix-Tree/)
```python

```

