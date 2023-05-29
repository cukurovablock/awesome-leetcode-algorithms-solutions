# [Brute Force to solve the Two-Sum Problem on Java language](https://leetcode.com/problems/two-sum/solutions/3576463/less-than-o-n-2-time-complexity-in-java)

## Approach
The brute-force approach to solving the two-sum problem involves checking every possible pair of elements in the array and comparing their sum to the target. This can be achieved by using two nested loops, where each loop iterates through all the elements in the array. In each iteration, the current pair of elements is checked to see if their sum is equal to the target. If a match is found, the indices of the elements are stored and returned as the solution. The idea is to go through all the possible combinations of elements and check if any of them add up to the target. It's a straightforward approach that doesn't require any complex algorithms or data structures, making it easy to understand and implement.

## Complexity

- Time complexity: O(n)
- Space complexity: O(1)
## Code

``` java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int tempNumber = target - nums[0];
        for(int i = 1, k = 0; i <= nums.length - 1;){
            if(tempNumber == nums[i]) {
                return new int[]{k, i};
            }
            if(i == nums.length - 1) {
                k++;
                i = k;
                tempNumber = target - nums[k];
            }
            i++;
        }
        return null;
    }
}
```
