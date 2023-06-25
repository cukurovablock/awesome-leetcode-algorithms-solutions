# [✅ Iteratively solving the 🧑🏻‍💻 Reverse Linked List Problem on 🐍 Python language](https://leetcode.com/problems/reverse-linked-list/solutions/3681527/iteratively-solving-the-reverse-linked-list-problem-on-python-language/)

## 🧑🏻‍💻 Approach

The problem is to reverse a linked list. We will use an iterative method for this. We start by initializing two pointers: one (`prev`) that points to None (as the last node in a reversed list should point to None) and another (`curr`) that points to the head node. The idea is to traverse the list and for each node, save its next node, update its next pointer to the node before it (which is `prev`), and then move `prev` and `curr` one step forward. In the end, `prev` will point to the new head, which is the last node in the original list.

## 🔐 Code

``` python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        prev, curr = None, head
        
        while curr:
            nxt = curr.next
            curr.next = prev
            prev = curr
            curr = nxt
            
        return prev
```

## 🧩 Complexity

- Time complexity:
The time complexity of this approach is $O(n)$ where n is the length of the linked list. This is because we are running a loop to traverse through the list once.

- Space complexity:
The space complexity is $O(1)$ as we are only using a constant amount of space to store our variables (prev, curr, and nxt), regardless of the size of the input linked list.
