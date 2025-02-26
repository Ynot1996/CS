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

### Hard
- [Merge K Sorted Lists](#Merge-K-Sorted-Lists)
- [Reverse Nodes in k-Group](#Reverse-Nodes-in-k-Group)
- [LRU Cache](#LRU-Cache)
- [Copy List with Random Pointer](#Copy-List-with-Random-Pointer)
- [Remove Duplicate Nodes](#Remove-Duplicate-Nodes)
- [Linked List in Binary Tree](#Linked-List-in-Binary-Tree)

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
## Basic
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

<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Easy-->
## Reverse Linked List
[206](https://leetcode.com/problems/Reverse-Linked-List/)

1\. Iterative Method

- Python
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

- Java
```java
public ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode curr = head;
        while (curr != null) {
            ListNode Nxt = curr.next;
            curr.next = prev;
            prev = curr;
            curr = Nxt;
        }
        return prev;
    }
}
```

2\. Recursive Method

```python

```
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Medium-->
## Add Two Numbers
[2](https://leetcode.com/problems/Add-Two-Numbers/)

```java
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(-1);
        ListNode curr = dummy;
        int carry = 0;

        while (l1!=null || l2!= null){
            int sum = 0;
            if (l1==null){
                sum = l2.val + carry;
                l2 = l2.next;
            } else if (l2==null){
                sum = l1.val + carry;
                l1 = l1.next;
            } else {
                sum = l1.val + l2.val +carry;
                l1 = l1.next;
                l2 = l2.next;
            }
            int num = sum % 10;
            carry = sum / 10;
            curr.next = new ListNode(num);
            curr = curr.next;
        }
        if (carry == 1){
            curr.next = new ListNode(1);
        }
        return dummy.next;
    }
}
```
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Hard-->
## Merge K Sorted Lists
[23](https://leetcode.com/problems/Merge-K-Sorted-Lists/)
