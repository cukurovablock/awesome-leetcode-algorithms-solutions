# [✅ Lowercase Alphanumeric to solve the 🧑🏻‍💻 Valid Palindrome Problem on 🐍 Python language](https://leetcode.com/problems/valid-palindrome/solutions/3602273/lowercase-alphanumeric-to-solve-the-valid-palindrome-problem-on-python-language/)

## 🧑🏻‍💻 Approach
<!-- Describe your approach to solving the problem. -->
The code determines if a given string is a palindrome by first extracting only the alphanumeric characters and converting them to lowercase. It then compares the characters at corresponding positions from the start and end of the string. If any pair of characters doesn't match, the string is not a palindrome. Otherwise, if all pairs match, the string is a palindrome. The code assumes ASCII characters in the input string.

## 🔐 Code

``` python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        alphanumeric = ""
        for c in s:
            if self.isAlphanum(c): # or you can use c.isalnum():
                alphanumeric += c.lower()

        length = len(alphanumeric)

        # we need to check half of string
        for i in range(length // 2): # // is floor division operator 10 // 3 = 3
            if alphanumeric[i] != alphanumeric[length - i - 1]:
                return False

        return True

    def isAlphanum(self, c):
        return (
            ord("A") <= ord(c) <= ord("Z")
            or ord("a") <= ord(c) <= ord("z")
            or ord("0") <= ord(c) <= ord("9")
        )
```

## 🧩 Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $O(n)$ -->
The time complexity of the code is $O(n)$, where n is the length of the input string. The code iterates through each character of the string once to extract the alphanumeric characters, and then performs a comparison for the first half of the alphanumeric string. Since the number of iterations is directly proportional to the length of the input string, the time complexity is linear.

- Space complexity:
<!-- Add your space complexity here, e.g. $O(n)$ -->
The space complexity of the code is also $O(n)$, where n is the length of the input string. This is because the code creates a new string `alphanumeric` to store the alphanumeric characters from the input string. The length of the `alphanumeric` string can be at most equal to the length of the input string, so the space complexity is linear.
