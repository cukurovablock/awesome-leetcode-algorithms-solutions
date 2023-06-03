# [✅ Counts the Frequencies to solve the 🧑🏻‍💻 Group Anagram Problem on 🐍 Python language](https://leetcode.com/problems/group-anagrams/solutions/3587269/counts-the-frequencies-to-solve-the-group-anagram-problem-on-python-language/)

## 🧑🏻‍💻 Approach
<!-- Describe your approach to solving the problem. -->
the approach counts the occurrences of each letter in the words and groups the anagrams together based on their letter counts using a dictionary.

## 🔐 Code

``` python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        ans = collections.defaultdict(list) 
        # default list dictionary if it is empty it returns empty list

        for s in strs: # iterate of words
            count = [0] * 26 # 26 zero list for alpahabet
            for c in s: # iterate of letters
                count[ord(c) - ord("a")] += 1 # ord(c) gives ascii value 
            ans[tuple(count)].append(s) # add to word to list that related with key ()whic is count list)
           
            """
                {
                    (1,2,...,1,...): [
                        "bat"
                    ],
                    (1,...,1,...,1,...): [
                        "nat",
                        "tan"
                    ],
                    (1,...,1....,1,...): [
                       "ate",
                       "eat",
                       "tea"
                    ],
                }
            """

        return ans.values()
```

## 🧩 Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $O(n)$ -->
The time complexity of the solution is $O(n \* k)$, where n is the number of words in the input list `strs` and k is the maximum length of the words. In the worst case, where all words have the same maximum length, the time complexity simplifies to $O(n \* m)$, where m is the maximum length of the words. The constant-time operations performed inside the loops do not significantly impact the overall time complexity. Thus, the solution has a linear time complexity with respect to the size of the input list and the maximum length of the words.

- Space complexity:
<!-- Add your space complexity here, e.g. $O(n)$ -->
The space complexity of the solution is $O(n)$, where n is the number of words in the input list `strs`. The `ans` dictionary, which stores the groups of anagrams, is the main factor contributing to the space complexity. The additional space used for the `count` list and other variables is constant and does not significantly affect the overall space requirement. Hence, the space complexity is linear with respect to the size of the input list.
