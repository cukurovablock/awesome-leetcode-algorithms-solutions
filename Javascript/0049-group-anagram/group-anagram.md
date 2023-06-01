# [🔥🔠 Anagram Grouping: Explore the Shortest Path with JavaScript! 🧩🔎✨](https://leetcode.com/problems/group-anagrams/solutions/3586360/anagram-grouping-explore-the-shortest-path-with-javascript/)


## Approach
The code follows the following approach to group anagrams:

1- Create an empty object anagramGroups. This object will be used to store the anagram groups.

2- Iterate through each string `(str)` in the input array `(strs)`.

3- Sort the characters of the string `(str)` in alphabetical order. This will ensure that all anagrams have the same sorted string representation. Convert the sorted string back to its original form using `.join('')`.

4- Check if the sorted string exists as a key in the `anagramGroups` object. If it exists, push the original string `(str)` to the corresponding group array. If it doesn't exist, create a new `key-value` pair in the anagramGroups object, with the sorted string as the key and an array containing the original string as the value.

5- After iterating through all strings, convert the values of the anagramGroups object into an array using Object.values`(anagramGroups)`. This will give an array of arrays, where each inner array represents an anagram group.

6- Sort the resulting array of anagram groups based on their lengths using the `.sort()` method. The comparison function `(a, b) => a.length - b.length` compares the lengths of the inner arrays and sorts them in ascending order.

7- Return the sorted array of anagram groups.

This approach uses the sorted string representation of each string to group anagrams together. By comparing the sorted strings, we can identify which strings belong to the same anagram group.
## Complexity

- Time complexity:O(n∗(mlogm))+O(nlogn)

The time complexity of this code can be analyzed as follows:

Loop (for...of): This loop iterates over the strs array, so the complexity is `O(n)`, where n is the length of the strs array.

String Operations: In each iteration of the loop, the following operations are performed on the current string str:

.split(''): Converting the string into an array of characters. This operation has a complexity of `O(m)`, where m is the length of the string.
.sort(): Sorting the array of characters. The sorting algorithm used can vary depending on the JavaScript engine, but typically a fast sorting algorithm like quicksort is used, which has an average complexity of `O(mlogm)`.
`.join('')`: Converting the sorted array of characters back into a string. This operation also has a complexity of `O(m)`, where m is the length of the string.
Adding to the Object: In each iteration of the loop, the sorted string (sortedStr) is used to access the groupAnagram object and add the string to the corresponding array. This operation has a complexity of `O(1)`.

Result Creation and Sorting: After the loop is completed, the values of the groupAnagram object are converted into an array using `Object.values()`. This operation has a complexity of `O(n)`. Then, the array is sorted based on the lengths of the groups using `.sort()`. The sorting operation has an average complexity of `O(nlogn)` using a fast sorting algorithm like quicksort.

Therefore, the overall time complexity of the code is `O(n∗(mlogm))+O(nlogn)`, where n is the length of the strs array and m is the average length of the strings.

-  Space complexity: O(n∗m)
  
The space complexity of the given code is `O(n∗m)`, where n is the length of the strs array and m is the average length of the strings.

In the code, a groupAnagram object is used to store the groups of anagrams. The space required by this object depends on the number of distinct anagram groups. In the worst case scenario, where there are no anagrams and all strings are distinct, each string will be considered as a separate group, resulting in n distinct groups. Therefore, the space required by the groupAnagram object is proportional to the number of strings, which is `O(n)`.

Additionally, the result array is created to store the grouped anagrams. The number of elements in this array is equal to the number of anagram groups, which can be at most n in the worst case scenario. Hence, the space required by the result array is also `O(n)`.

Overall, the space complexity is `O(n∗m)` due to the groupAnagram object and the result array.
## Code

``` Javascript
var groupAnagrams = function(strs) {
let groupAnagram = {};

for (let str of strs) {
  let sortedStr = str.split('').sort().join('');

  if (groupAnagram[sortedStr]) groupAnagram[sortedStr].push(str);
    
   else groupAnagram[sortedStr] = [str];
}

let result = Object.values(groupAnagram);

result.sort((a, b) => a.length - b.length);

return result;
    
};
```
