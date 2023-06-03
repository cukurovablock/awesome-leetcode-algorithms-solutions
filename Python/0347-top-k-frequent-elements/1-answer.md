# [✅ Counts and Sort to solve the 🧑🏻‍💻 Top K Frequent Elements Problem on 🐍 Python language](https://leetcode.com/problems/top-k-frequent-elements/solutions/3594131/counts-and-sort-to-solve-the-top-k-frequent-elements-problem-on-python-language/)

## 🧑🏻‍💻 Approach
<!-- Describe your approach to solving the problem. -->
1. Create an empty dictionary called `hashSet` to store the frequencies of elements.
2. Iterate through the `nums` list using a for loop.
3. For each element `num` in the `nums` list, update its frequency in the `hashSet` dictionary by incrementing the value associated with the key `num`. If the key doesn't exist, set its value to 1.
4. Convert the `hashSet` dictionary into a list of tuples called `freq_list` using the `items()` method. Each tuple in `freq_list` contains an element from the `nums` list and its corresponding frequency.
5. Sort the `freq_list` in descending order based on the second element (frequency) of each tuple. This is achieved using the `sort()` method with a lambda function as the `key` argument.
6. Extract the first `k` elements from the sorted `freq_list` and store them in the `result` list. The first element of each tuple in `freq_list` represents the element from `nums`.
7. Return the `result` list containing the top `k` frequent elements.

## 🔐 Code

``` python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        hashSet = {} #create empty dict

        #hashSet = {1: 3, 2: 5, 4: 2}
        for i in range(len(nums)):
            hashSet[nums[i]] = 1 + hashSet.get(nums[i], 0)

        # freq_list = [(1,3),(2,5),(4,2)]    
        freq_list = list(hashSet.items())
        # freq_list = [(2,5),(1,3),(4,2)]  
        freq_list.sort(key=lambda x: x[1], reverse=True) #x represent each tuple

        # result[2,1]
        result = [x[0] for x in freq_list[:k]]
        return result
```

## 🧩 Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $O(n)$ -->
The time complexity of this code is dominated by the sorting operation performed on `freq_list`. Sorting a list of length `n` has a time complexity of O(n log n). Therefore, the overall time complexity of the code is O(n log n), where `n` is the length of the input list `nums`.

- Space complexity:
<!-- Add your space complexity here, e.g. $O(n)$ -->
The space complexity is determined by the space used to store the `hashSet` dictionary and the `freq_list`. The `hashSet` dictionary will have a space complexity of O(n) in the worst case, where `n` is the length of the input list `nums`. The `freq_list` will also have a space complexity of O(n) because it stores all the elements and their frequencies. Additionally, the `result` list will have a space complexity of O(k) since it stores the top `k` frequent elements. Therefore, the overall space complexity is O(n + k), where `n` is the length of the input list `nums` and `k` is the parameter passed to the method.
