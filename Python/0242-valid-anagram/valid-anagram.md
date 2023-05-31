# [✅ Counts the Frequencies to solve the 🧑🏻‍💻 Valid Anagram Problem on 😎 Python language](https://leetcode.com/problems/valid-anagram/solutions/3583443/counts-the-frequencies-to-solve-the-valid-anagram-problem-on-python-language/)

## Approach
<!-- Describe your approach to solving the problem. -->
In summary, the approach counts the frequencies of characters in both strings using dictionaries and checks if the character frequencies in s and t are the same. If the character frequencies match, the method returns `True`, indicating that t is an anagram of s. Otherwise, it returns `False`.

## Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $O(n)$ -->
The time complexity of the solution is $O(n)$, where n is the length of the input strings `s` and `t`. The `for` loop iterates over the strings once, performing constant-time operations inside the loop. Since the loop iterates n times, the overall time complexity is linear with respect to the length of the strings.

- Space complexity:
<!-- Add your space complexity here, e.g. $O(n)$ -->
The space complexity of the solution is $O(n)$, where n is the length of the input strings `s` and `t`. The dictionaries `countS` and `countT` store the frequency of each character in their respective strings. In the worst case, if all characters are unique, the dictionaries would contain n key-value pairs. Therefore, the space required by the dictionaries is proportional to the length of the strings, resulting in a space complexity of $O(n)$.

## Code

``` python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        
        countS, countT = {}, {}

        """
        a => 3
        n => 2
        s => 1

        s => 1
        a => 3
        n => 2
        """

        for i in range(len(s)):
            # get value with key and add 1 to old value
            countS[s[i]] = 1 + countS.get(s[i], 0)
            countT[t[i]] = 1 + countT.get(t[i], 0)
        return countS == countT
```
