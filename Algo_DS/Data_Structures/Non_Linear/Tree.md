# Tree

### Tree Traversal 
DFS
- Easy
- [94. Binary Tree Inorder Traversal](#Binary-Tree-Inorder-Traversal)
- [144. Binary Tree Preorder Traversal](#Binary-Tree-Preorder-Traversal)
- [145. Binary Tree Postorder Traversal](#Binary-Tree-Postorder-Traversal)
- [226. Invert Binary Tree)](#Invert-Binary-Tree)
- [572. Subtree of Another Tree](#Subtree-of-Another-Tree)
  
- Medium
- [98. Validate Binary Search Tree](#Validate-Binary-Search-Tree)
- [105. Construct Binary Tree from Preorder and Inorder Traversal](#Construct-Binary-Tree-from-Preorder-and-Inorder-Traversal)
  
- Medium
- [297. Serialize and Deserialize Binary Tree](#Serialize-and-Deserialize-Binary-Tree)
  
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

### Invert Binary Tree
[226](https://leetcode.com/problems/Invert-Binary-Tree/)

```python
class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        if root is None:
            return None

        root.left, root.right = root.right, root.left

        self.invertTree(root.left)
        self.invertTree(root.right)

        return root
```

### Subtree of Another Tree
[572](https://leetcode.com/problems/Subtree-of-Another-Tree/)

NeetCode: https://youtu.be/E36O5SWp-LE?si=WRBqpMDRwc1CXwhK
```python
class Solution:
    def sameTree(self, s, t):
        if not s and not t:
            return True
        if s and t and s.val == t.val:
            return (self.sameTree(s.left, t.left) and self.sameTree(s.right, t.right))
        return False

    def isSubtree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        if not subRoot:
            return True
        if not root: 
            return False
        
        if self.sameTree(root, subRoot):
            return True
        
        return (self.isSubtree(root.left, subRoot) or self.isSubtree(root.right, subRoot))
```

### Validate Binary Search Tree
[98](https://leetcode.com/problems/Validate-Binary-Search-Tree/)

NeetCode: https://youtu.be/s6ATEkipzow?si=H7kzTt12JvOQmqCu
```python
class Solution:
    def isValidBST(self, root: Optional[TreeNode]) -> bool:

        def valid(node, left, right):
            if not node:
                return True

            if not (left < node.val < right):
                return False

            return (valid(node.left, left, node.val) and 
                    valid(node.right, node.val, right))

        return valid(root, float('-inf'), float('inf'))
```

### Serialize and Deserialize Binary Tree
[297](https://leetcode.com/problems/Serialize-and-Deserialize-Binary-Tree/)

```python
class Codec:

    def serialize(self, root):
        if not root:
            return "null"
        
        res = []

        def dfs(node):
            if not node:
                res.append("null")
                return
            res.append(str(node.val))
            dfs(node.left)
            dfs(node.right)
        
        dfs(root)
        return ",".join(res)

    def deserialize(self, data):
        values = iter(data.split(","))
         
        def dfs():
            val = next(values)
            if val == "null":
                return None
            node = TreeNode(int(val))
            node.left = dfs()
            node.right = dfs()
        
        return dfs()
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
class TrieNode:
    def __init__(self):
        self.children = {}
        self.endOfWord = False

class Trie:

    def __init__(self):
        self.root = TrieNode()

    def insert(self, word: str) -> None:
        cur = self.root

        for c in word:
            if c not in cur.children:
                cur.children[c] = TrieNode()
            cur = cur.children[c]
        cur.endOfWord = True

    def search(self, word: str) -> bool:
        cur = self.root
        
        for c in word:
            if c not in cur.children:
                return False
            cur = cur.children[c]
        return cur.endOfWord

    def startsWith(self, prefix: str) -> bool:
        cur = self.root
        
        for c in prefix:
            if c not in cur.children:
                return False
            cur = cur.children[c]
        return True
```

