# [HashMap Duplicate Array problem solution in Java language](https://leetcode.com/problems/contains-duplicate/solutions/3579963/hashmap-o-n-time-complexity-solution-in-java/)

## Intuition
Firstly, I have an idea which is iterated array with loop. I prefer foreach loop to visit every element of array. And then, i choose a data structure for hold a value with key of the array index. Hashmap or HashSet is good choice for time complexity and space complexity.

## Approach
I choose a Hashmap Data structure for hold array value to key of Hashmap. Because, it good at control to duplicate array value. What is the good at? It means that Hashmap hold key value pairs. If key added before, return **true**, if not return **false**.
## Complexity

- Time complexity: O(n)
- Space complexity: O(1)
## Code

``` java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        HashMap<Integer, Integer> duplicate = new HashMap<Integer, Integer>();
        for(int num : nums) {
            if(duplicate.containsKey(num)){
                return true;
            }
            duplicate.put(num, 1);
        }
        return false;
    }
}
```
