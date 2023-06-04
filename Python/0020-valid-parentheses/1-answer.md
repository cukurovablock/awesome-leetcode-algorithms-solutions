# [✅ Stack and Map to solve the 🧑🏻‍💻 Valid Parentheses on 🐍 Python language](https://leetcode.com/problems/valid-parentheses/solutions/3598423/stack-and-map-to-solve-the-valid-parentheses-on-python-language/)

## 🧑🏻‍💻 Approach
<!-- Describe your approach to solving the problem. -->
The approach used in this code is to iterate through the input string character by character. When an opening symbol is encountered, it is pushed onto the stack. When a closing symbol is encountered, it is checked against the top element of the stack. If they match, the opening symbol is popped from the stack. If they don't match or the stack is empty, it means the string is invalid. At the end, if the stack is empty, it means all symbols were properly matched, so the string is valid; otherwise, it is invalid.

## 🔐 Code

``` python
class Solution:
    def isValid(self, s: str) -> bool:
        #map close symbols to opening symbols
        # ) -> (
        # ] -> [
        # } -> {     
        hashMap = {")": "(", "]": "[", "}": "{"}
        stack = []

        for c in s: #iterate over string
            if c not in hashMap: # if it is opening symbol
                stack.append(c) # add to stack 
                continue
            # if it is closing symbol and
            # it stack is empty or
            # not correct closing symbol return false
            # stack[-1] -> gives top element on stack
            if not stack or stack[-1] != hashMap[c]:
                return False
            stack.pop() # otherwise pop from stack

        # if stack is empty return true else return false
        return not stack
```

## 🧩 Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $O(n)$ -->
The time complexity of this code is $O(n)$, where n is the length of the input string. This is because the code iterates through each character in the string once.

- Space complexity:
<!-- Add your space complexity here, e.g. $O(n)$ -->
The space complexity of this code is $O(n)$, where n is the length of the input string. In the worst case, if all the characters in the string are opening symbols, they will be stored in the stack. Therefore, the space required for the stack will be proportional to the length of the string.
