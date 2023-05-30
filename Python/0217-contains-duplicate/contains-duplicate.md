# [Hash Set to solve the Contains Duplicate Problem on Python language](https://leetcode.com/problems/contains-duplicate/solutions/3579958/hash-set-to-solve-the-contains-duplicate-problem-on-python-language/)

## Approach

We use hash set to efficiently check for duplicates in the array. It iterates through the numbers, adding each number to the set if it hasn't been encountered before. If a duplicate is found during the iteration, the code returns `True`; otherwise, it returns `False`.

## Complexity

- Time complexity:

The time complexity of the given code is $O(n)$, where n is the length of the input array `nums`. This is because the code iterates over each element in the array once, performing constant-time operations for each element. The `in` operator used to check if an element exists in the hash set, as well as the `add()` operation to insert an element into the hash set, both have an average time complexity of $O(1)$.

- Space complexity:
  
Space Complexity:
The space complexity of the given code is $O(n)$ in the worst case. This occurs when all elements in the input array nums are unique and need to be stored in the hash set. In such a scenario, the hash set would contain n elements. However, if there are duplicate elements present in the array, the space usage of the hash set would be smaller as it only stores unique elements.

## Code

``` python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashSet = set() 

        for n in nums:
            
            if n in hashSet:
                return True
            hashSet.add(n)

        return False
```
