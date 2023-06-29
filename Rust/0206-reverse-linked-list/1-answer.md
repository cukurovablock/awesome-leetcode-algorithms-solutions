# [✅ Iteratively solving the 🧑🏻‍💻 Reverse Linked List Problem on 🦀 Rust language]()

## 🧑🏻‍💻 Approach

The given code defines a struct `ListNode` that represents a node of a linked list. It has two fields: `val`, which stores the value of the node, and `next`, which is an `Option` containing the next node in the list.

The `impl` block contains an implementation for the `ListNode` struct. It defines a constructor function `new` that creates a new `ListNode` with the given value and initializes `next` to `None`.

The `reverse_list` function takes an `Option<Box<ListNode>>` as input, representing the head of a linked list, and returns the head of the reversed linked list.

Inside the function, two variables `current` and `previous` are initialized. `current` holds the current node being processed, and `previous` holds the reversed portion of the linked list.

The function enters a loop, where it iteratively reverses the linked list. It uses a combination of `while let` and `Option::take()` to move the current node (`node`) out of the Option and assign its next to `current`.

Within each iteration, the `next` node is temporarily stored, and the `next` field of the current node is set to `previous`, effectively reversing the pointer direction.

Finally, the `previous` node becomes the new `current` node, and the `next` node becomes the new `current` for the next iteration.

Once the loop completes, the reversed linked list is stored in `previous`, which now represents the new head of the reversed list, and it is returned.

## 🔐 Code

``` rust
// Definition for singly-linked list.
// #[derive(PartialEq, Eq, Clone, Debug)]
// pub struct ListNode {
//   pub val: i32,
//   pub next: Option<Box<ListNode>>
// }
// 
// impl ListNode {
//   #[inline]
//   fn new(val: i32) -> Self {
//     ListNode {
//       next: None,
//       val
//     }
//   }
// }
impl Solution {
    pub fn reverse_list(head: Option<Box<ListNode>>) -> Option<Box<ListNode>> {
        let mut current = head;
        let mut previous = None;

        while let Some(mut node) = current{
            let next = node.next.take();
            node.next=previous;
            previous = Some(node);
            current = next;
        }

        previous
    }
}
```
