# Linked List
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
### Easy
- [206. Reverse Linked List](#Reverse-Linked-List)
- [21. Merge Two Sorted Lists](#Merge-Two-Sorted-Lists)
- [141. Linked List Cycle](#Linked-List-Cycle)
- [203. Remove Linked List Elements](#Remove-Linked-List-Elements)
- [Palindrome Linked List](#Palindrome-Linked-List)

### Medium
- [2. Add Two Numbers](#Add-Two-Numbers)
- [328. Odd Even Linked List](#Odd-Even-Linked-List)
- [237. Delete Node in a Linked List](#Delete-Node-in-a-Linked-List)
- [Remove Nth Node From End of List](#Remove-Nth-Node-From-End-of-List)
- [Rotate List](#Rotate-List)
- [Partition List](#Partition-List)
- [Sort List](#Sort-List)
- [Reorder List](#Reorder-List)
- [Linked List Cycle II](#Linked-List-Cycle-II)
- [Intersection of Two Linked Lists](#Intersection-of-Two-Linked-Lists)

### Hard
- [23. Merge K Sorted Lists](#Merge-K-Sorted-Lists)
- [Reverse Nodes in k-Group](#Reverse-Nodes-in-k-Group)
- [LRU Cache](#LRU-Cache)
- [Copy List with Random Pointer](#Copy-List-with-Random-Pointer)
- [Remove Duplicate Nodes](#Remove-Duplicate-Nodes)
- [Linked List in Binary Tree](#Linked-List-in-Binary-Tree)

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
class Solution{
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
