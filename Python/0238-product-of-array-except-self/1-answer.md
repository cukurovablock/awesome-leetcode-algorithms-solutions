# [✅ Prefix and Postfix to solve the 🧑🏻‍💻 Product of Array Except Self Problem on 🐍 Python language](https://leetcode.com/problems/product-of-array-except-self/solutions/3598205/prefix-and-postfix-to-solve-the-product-of-array-except-self-problem-on-python-language/)

## 🧑🏻‍💻 Approach
<!-- Describe your approach to solving the problem. -->
The approach used in the code is as follows:

1. Initialize a result list `res` with all elements set to 1.
2. Perform a forward pass through the input list `nums`:
   - Update each element in `res` with the product of all elements to the left of it.
3. Perform a backward pass through the input list `nums`:
   - Update each element in `res` by multiplying it with the product of all elements to the right of it.
4. Return the resulting list `res`, which contains the product of all elements in `nums` except the element at each index `i`.

This approach leverages the concept of prefix and postfix products to calculate the desired result efficiently in a single pass in each direction.

## 🔐 Code

``` python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        res = [1] * (len(nums)) #[1,1,1,1]

        prefix = 1
        # [1,2,3,4]
        for i in range(len(nums)):
            res[i] = prefix 
            # [1,1,1,1]
            # [1,1,1,1]
            # [1,1,2,1]
            # [1,1,2,6]
            prefix *= nums[i]
            # 1
            # 2
            # 6
            # 24

        postfix = 1
        # [1,2,3,4]
        for i in range(len(nums) - 1, -1, -1):
            res[i] *= postfix
            # [1,1,2,6*1]
            # [1,1,2*4,6]
            # [1,12,8,6]
            # [24,12,8,6]
            postfix *= nums[i]
            # 4
            # 12
            # 24
            # 24

        return res
        # [24,12,8,6]    
```

## 🧩 Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $O(n)$ -->
The time complexity of the given code is $O(N)$, where N is the length of the input list `nums`. This is because the code performs two passes through the input list, each taking O(N) time. Therefore, the overall time complexity is $O(N + N)$, which simplifies to $O(N)$.

- Space complexity:
<!-- Add your space complexity here, e.g. $O(n)$ -->
The space complexity of the code is $O(N)$ as well. This is because it uses an additional list `res` of the same length as `nums` to store the results. Therefore, the space required is proportional to the length of the input list `nums`, resulting in a space complexity of $O(N)$. However because of the output array does not count as extra space for space complexity analysis we can say Space complexity is $O(1)$
