# Linked List
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [Reverse Linked List](#Reverse-Linked-List)
- [Merge Two Sorted Lists](#Merge-Two-Sorted-Lists)
- [Linked List Cycle](#Linked-List-Cycle)
- [Remove Linked List Elements](#Remove-Linked-List-Elements)
- [Palindrome Linked List](#Palindrome-Linked-List)

### Medium
- [Add Two Numbers](#Add-Two-Numbers)
- [Odd Even Linked List](#Odd-Even-Linked-List)
- [Delete Node in a Linked List](#Delete-Node-in-a-Linked-List)
- [Remove Nth Node From End of List](#Remove-Nth-Node-From-End-of-List)
- [Rotate List](#Rotate-List)
- [Partition List](#Partition-List)
- [Sort List](#Sort-List)
- [Reorder List](#Reorder-List)
- [Linked List Cycle II](#Linked-List-Cycle-II)
- [Intersection of Two Linked Lists](#Intersection-of-Two-Linked-Lists)

### Medium
- [Merge K Sorted Lists](#Merge-K-Sorted-Lists)
- [Reverse Nodes in k-Group](#Reverse-Nodes-in-k-Group)
- [LRU Cache](#LRU-Cache)
- [Copy List with Random Pointer](#Copy-List-with-Random-Pointer)
- [Remove Duplicate Nodes](#Remove-Duplicate-Nodes)
- [Linked List in Binary Tree](#Linked-List-in-Binary-Tree)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
## 基礎鏈表操作
1\. 創建與遍歷節點

- 創建節點
  
```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
```

- 遍歷鏈表
   
```python
def traverse(head):
    while head:
        print(head.val, end=' -> ')
        head = head.next
    print("None")
```

2\. 插入與刪除節點 
   
- 在鏈表中間插入節點

```python
new_node = ListNode(5)
new_node.next = prev_node.next
prev_node.next = new_node
```

- 刪除節點
  
```python
prev_node.next = prev_node.next.next
```

3\. 反轉鏈表
   
- 雙指針法

```python
def reverse_list(head):
    prev, curr = None, head
    while curr:
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node
    return prev
```

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Easy-->
## Reverse Linked List
[206](https://leetcode.com/problems/Reverse-Linked-List/)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Medium-->
## Add Two Numbers
[2](https://leetcode.com/problems/Add-Two-Numbers/)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Hard-->
## Merge K Sorted Lists
[23](https://leetcode.com/problems/Merge-K-Sorted-Lists/)
