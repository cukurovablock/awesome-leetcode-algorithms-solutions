# [✅ Two Pointer to solve the 🧑🏻‍💻 Two Sum 2 Problem on 🐍 Python](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/solutions/3610884/two-pointer-to-solve-the-two-sum-2-problem-on-python/)

## 🧑🏻‍💻 Approach
<!-- Describe your approach to solving the problem. -->
The approach in the given code is to use a two-pointer technique to find a pair of numbers in a sorted array that add up to a target value. The pointers start from the beginning and end of the array and move towards each other based on whether the current sum is greater or smaller than the target. This approach takes advantage of the sorted nature of the array to efficiently narrow down the search space and find the desired pair in linear time.

## 🔐 Code

``` python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        left, right = 0, len(numbers) - 1  # Initialize the left and right pointers

        while right > left:  # Continue until the pointers meet or cross
            if numbers[left] + numbers[right] > target:  # Current pair is too large
                right -= 1  # Decrement right pointer
            elif numbers[left] + numbers[right] < target:  # Current pair is too small
                left += 1  # Increment left pointer
            else:  # Found the solution
                return [left + 1, right + 1]  # Return indices (adjusted by adding 1)

        # If no solution is found, return an empty list or handle it as needed
        return []
```

## 🧩 Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $O(n)$ -->
The time complexity of the given code is $O(n)$, where n is the number of elements in the input array. Since the code uses a two-pointer approach and iterates through the array only once, the time complexity is linear.

- Space complexity:
<!-- Add your space complexity here, e.g. $O(n)$ -->
The space complexity of the code is $O(1)$ because it uses a constant amount of additional space. It does not allocate any new data structures that scale with the input size. The code only uses a fixed number of variables to store the pointers and the result, so the space complexity is constant.
