# [👨‍🏫Simple "Valid Anagram" Solution in Javascript 👌](https://leetcode.com/problems/valid-anagram/solutions/3583388/simple-valid-anagram-solution-in-javascript/)

## Approach
<!-- Describe your approach to solving the problem. -->
This code snippet contains a function that checks if two given strings are anagrams of each other. Here's how it works:

1-First, if the lengths of the two strings are different, meaning they are not of the same length, the function returns `false`.

2-Then, both strings are converted into arrays of characters using the `split('')` method, and each array is sorted alphabetically using the `sort()` method. This gives us the sorted versions of both strings.

3-Next, a loop is initiated for each element in the ``sorted_T`` array, and each element is compared with the corresponding element in the `sorted_S` array.

4-If any element doesn't match during the comparison (meaning the characters at the respective indexes in the sorted arrays are different), the function returns `false`.

5-If all elements match until the end of the loop (meaning both strings have the same characters), the function returns `true`.

## Complexity

- Time complexity:O(n log n)
<!-- Add your time complexity here, e.g. $O(n)$ -->


- Space complexity:O(1)
<!-- Add your space complexity here, e.g. $O(n)$ -->


## Code

``` javascript
var isAnagram = function(s, t) {

    if (s.length !== t.length) return false;
    
    const sorted_S = s.split('').sort();
    const sorted_T = t.split('').sort();
    
    for (let i = 0; i < sorted_T.length; i++) {
      
      if (sorted_S[i] !== sorted_T[i]) return false; 
        
    }
    
    return true;
  
    
};
```