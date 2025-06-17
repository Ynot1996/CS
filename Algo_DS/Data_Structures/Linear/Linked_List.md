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
- [19. Remove Nth Node From End of List](#Remove-Nth-Node-From-End-of-List)
- [328. Odd Even Linked List](#Odd-Even-Linked-List)
- [237. Delete Node in a Linked List](#Delete-Node-in-a-Linked-List)
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

2\. Recursive Method

```java
class Solution {
    public ListNode reverseList(ListNode head) {
        if (head==null||head.next==null){
            return head;
        }
        ListNode reversedListHead = reverseList(head.next);
        head.next.next = head;
        head.next = null;
        return reversedListHead;
    }
}
```
## Merge Two Sorted Lists
[21](https://leetcode.com/problems/Merge-Two-Sorted-Lists/)

```java
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode dummy = new ListNode(0);
        ListNode tail = dummy;

        while (list1!=null && list2!=null){
            if (list1.val<list2.val){
                tail.next = list1;
                list1 = list1.next;
            } else {
                tail.next = list2;
                list2 = list2.next;
            }
            tail = tail.next;
        }

        tail.next = (list1 != null) ? list1 : list2;

        return dummy.next;
    }
}
```
## Linked List Cycle
[141](https://leetcode.com/problems/Linked-List-Cycle/)

This code implements Floyd’s Cycle Detection Algorithm, which uses two pointers—slow moving one step at a time and fast moving two steps—to traverse the linked list, ensuring that if a cycle exists, fast will inevitably catch up to slow within the loop, while if no cycle exists, fast will eventually reach null, making this an efficient O(n) time and O(1) space solution.

```java
public class Solution {
    public boolean hasCycle(ListNode head) {
        if (head == null || head.next == null) {
            return false; 
        }
        
        ListNode slow = head;
        ListNode fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;     
            fast = fast.next.next;  

            if (slow == fast) { 
                return true;
            }
        }
        
        return false; 
    }
}
```
## Remove Linked List Elements
[203](https://leetcode.com/problems/Remove-Linked-List-Elements/)

```java
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;

        while (head!=null){
            if (head.val != val){
                curr.next = head;
                curr = curr.next;
            }
            head = head.next;
        }
        curr.next = null;
        
        return dummy.next;
    }
}
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
## Remove Nth Node From End of List
[19](https://leetcode.com/problems/Remove-Nth-Node-From-End-of-List/)

```python
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        dummy = ListNode(0)
        dummy.next = head
        current = dummy
        length = 0

        while current:
            length += 1
            current = current.next

        current_2 = dummy
        for i in range(length - n - 1):
            current_2 = current_2.next
        
        current_2.next = current_2.next.next

        return dummy.next
```
## Odd Even Linked List
[328](https://leetcode.com/problems/Odd-Even-Linked-List/)

```java
class Solution {
    public ListNode oddEvenList(ListNode head) {
        if (head==null || head.next==null) return head;

        ListNode odd = head;
        ListNode even = head.next;
        ListNode evenHead = even;

        while (even != null && even.next != null){
            odd.next = even.next;
            odd = odd.next;
            even.next = odd.next;
            even = even.next;
        }

        odd.next = evenHead;
        return head;
    }
}
```
## Delete Node in a Linked List
[237](https://leetcode.com/problems/Delete-Node-in-a-Linked-List/)

```java
class Solution {
    public void deleteNode(ListNode node) {
        node.val = node.next.val;
        node.next = node.next.next;
    }
}
```
<!------------------------------------------------------------------------------------------------------------------------------------------------------>
<!--Hard-->
## Merge K Sorted Lists
[23](https://leetcode.com/problems/Merge-K-Sorted-Lists/)
