# [✅ Double Stack to solve the 🧑🏻‍💻 Min Stack Problem on 🐍 Python language](https://leetcode.com/problems/min-stack/solutions/3606186/double-stack-to-solve-the-min-stack-problem-on-python-language/)

## 🧑🏻‍💻 Approach
<!-- Describe your approach to solving the problem. -->
The `MinStack` class is designed to maintain a stack of values while efficiently retrieving the minimum value at any time. It achieves this by using an additional stack, `minStack`, which keeps track of the minimum value encountered so far. Whenever a new value is pushed onto the stack, the minimum value between the new value and the current minimum is stored in `minStack`. This approach allows constant time retrieval of the minimum value by accessing the top of `minStack`.

## 🔐 Code

``` python
class MinStack:

    def __init__(self):
        self.stack = []
        self.minStack = []        

    def push(self, val: int) -> None:
        self.stack.append(val)
        #if minStack is non empty compare it with val and take min 
        # otherwise take val (or val) (which means they are same)
        val = min(val, self.minStack[-1] if self.minStack else val) 
        self.minStack.append(val)

    def pop(self) -> None:
        self.stack.pop()
        self.minStack.pop()
        
    def top(self) -> int:
        return self.stack[-1]

    def getMin(self) -> int:
        return self.minStack[-1]


# Your MinStack object will be instantiated and called as such:
# obj = MinStack()
# obj.push(val)
# obj.pop()
# param_3 = obj.top()
# param_4 = obj.getMin()
```

## 🧩 Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $O(n)$ -->
The time complexity of the `push`, `pop`, `top`, and `getMin` operations in the `MinStack` class is O(1). These operations involve only basic stack operations such as appending, popping, and accessing the top element, which all have constant time complexity.

- Space complexity:
<!-- Add your space complexity here, e.g. $O(n)$ -->
The space complexity of the `MinStack` class is O(n), where n is the number of elements stored in the stack. Both the `stack` and `minStack` lists grow linearly with the number of elements pushed onto the stack. Hence, the space required is proportional to the number of elements in the stack.
