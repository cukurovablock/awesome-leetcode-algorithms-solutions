# [Basic JavaScript Solution of "Contains Duplicate"](https://leetcode.com/problems/contains-duplicate/solutions/3580102/basic-javascript-solution-of-contains-duplicate/)


## Approach
The code snippet you provided uses a sorting-based approach to check for duplicates in the given array. It does not utilize a hash map or brute force method.

Here's an explanation of the approach used in the code:

1. The code starts by sorting the array `nums` using the `sort()` method. Sorting the array allows duplicate elements to be adjacent to each other.
2. Then, the code iterates through the sorted array from index 0 to `nums.length - 1` (excluding the last element).
3. Within the loop, it compares the current element `nums[i]` with the next element `nums[i + 1]`.
4. If the current element is equal to the next element, it means there is a duplicate present. In this case, the code returns `true` to indicate the presence of duplicates.
5. If no duplicates are found after iterating through the entire array, the code returns `false` to indicate that there are no duplicates.

In summary, the provided code uses a sorting-based approach to check for duplicates. It sorts the array and then compares adjacent elements to identify duplicates. It does not use a hash map or brute force method to solve the problem.
## Complexity

- Time complexity: O(n log n)
- Space complexity: O(1)
## Code

``` Javascript
var containsDuplicate = function(nums) {
    nums.sort();
    for (let i = 0; i < nums.length - 1; i++) {
        if (nums[i] === nums[i + 1]) {
            return true;
        }
    }
    return false;  
};
```
