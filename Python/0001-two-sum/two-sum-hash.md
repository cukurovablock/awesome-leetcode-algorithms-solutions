# [Hash Table to solve the Two-Sum Problem on Python language](https://leetcode.com/problems/two-sum/solutions/3577066/hash-table-to-solve-the-two-sum-problem-on-python-language/)

## Approach

The approach to solve the two-sum problem in Python involves using a dictionary (hash map) to store the previously encountered numbers and their indices.

We iterate through the given list of numbers using the `enumerate()` function to access both the index and the value of each number. For every number, we calculate the difference between the target and the current number.

If the difference is already present in the dictionary, it means we have found a pair of numbers whose sum is equal to the target. We can retrieve the index of the previously encountered number from the dictionary and return it along with the current index.

If the difference is not in the dictionary, we add the current number and its index to the dictionary. This way, if a subsequent number complements the current number to reach the target, we can easily retrieve the indices of the two numbers.

## Complexity

- Time Complexity:

The time complexity of this approach is O(n), where n is the size of the input list. We iterate through the list once, performing constant time operations for each element.

- Space Complexity:

The space complexity is also O(n) because, in the worst case, we might need to store all the numbers in the dictionary.

## Code

``` python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        prevMap = {}  # key -> value

        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i
```
