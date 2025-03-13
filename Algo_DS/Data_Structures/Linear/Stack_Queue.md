# Stack and Queue

### Stack
Easy
- [144. Binary Tree Preorder Traversal](#Binary-Tree-Preorder-Traversal)
- [145. Binary Tree Postorder Traversal](#Binary-Tree-Postorder-Traversal)
- [283. Binary Tree Inorder Traversal](#Binary-Tree-Inorder-Traversal)


### Queue
Easy
- [232. Implement Queue using Stacks](#Implement-Queue-using-Stacks)
- [346. Moving Average from Data Stream](#Moving-Average-from-Data-Stream)
- [933. Number of Recent Calls](#Number-of-Recent-Calls)
  
Medium
- [622. Design Circular Queue](#Design-Circular-Queue)
- [752. Open the Lock](#Open-the-Lock)
- [994. Rotting Oranges](#Rotting-Oranges)
  
Hard   
- [239. Sliding Window Maximum](#Sliding-Window-Maximum)
- [460. LFU Cache](#LFU-Cache)
- [1293. Shortest Path in a Grid](#Shortest-Path-in-a-Grid)

## Binary Tree Preorder Traversal
[144](https://leetcode.com/problems/binary-tree-preorder-traversal/)

Given the root of a binary tree, return the preorder traversal of its nodes' values.

Method: Recursive<br>

```java
class Solution {
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        dfs(root, result);
        return result;
    }
    private void dfs(TreeNode node, List<Integer> result){
        if (node == null) return;
        result.add(node.val);
        dfs(node.left, result);
        dfs(node.right, result);
    }
}
```

## Binary Tree Postorder Traversal
[145](https://leetcode.com/problems/binary-tree-postorder-traversal/)

Given the root of a binary tree, return the postorder traversal of its nodes' values.

Method: Stack<br>

```java

```

## Binary Tree Inorder Traversal
[283](https://leetcode.com/problems/binary-tree-inorder-traversal/)

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
## Implement Queue using Stacks
[232](https://leetcode.com/problems/Implement-Queue-using-Stacks/)

```python
class MyQueue:

    def __init__(self):
        self.s1 = []
        self.s2 = []

    def push(self, x: int) -> None:
        self.s1.append(x)

    def pop(self) -> int:
        if not self.s2:
            while self.s1:
                self.s2.append(self.s1.pop())
        return self.s2.pop()

    def peek(self) -> int:
        if not self.s2:
            while self.s1:
                self.s2.append(self.s1.pop())
        return self.s2[-1]

    def empty(self) -> bool:
        return max(len(self.s1), len(self.s2)) == 0
```

## Moving Average from Data Stream
[346](https://leetcode.com/problems/Moving-Average-from-Data-Stream/)

```python

```
