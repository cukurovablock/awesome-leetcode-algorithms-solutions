# [✅ Recursively solving the 🧑🏻‍💻 Reverse Linked List Problem on 🐍 Python language](https://leetcode.com/problems/reverse-linked-list/solutions/3681605/recursively-solving-the-reverse-linked-list-problem-on-python-language/)

## 🧑🏻‍💻 Approach

The problem is to reverse a linked list. This time, we'll use a recursive method for this. We start by checking if the current node (initially the head) or its next node is None. If it is, we return the current node because it will be the new head of the reversed list. If not, we make a recursive call to the function with the next node. The idea here is that in each recursive call, we are getting the reversed list for the remaining nodes, and we just need to update the next pointer of the next node to point to the current node and update the next pointer of the current node to None.

## 🔐 Code

``` python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        if not head or not head.next:
            return head

        newHead = self.reverseList(head.next)
        head.next.next = head
        head.next = None
        
        return newHead
```

## 🧩 Complexity

- Time complexity:
The time complexity of this approach is $O(n)$ where n is the length of the linked list. This is because each recursive call processes one node of the list, and there are n nodes in total.

- Space complexity:
The space complexity is $O(n)$, where n is the length of the linked list. This is because each recursive call is added to the call stack, and in the worst-case scenario, if the list has n nodes, there would be n recursive calls, thus n additions to the call stack. So the space complexity is proportional to the length of the list.
