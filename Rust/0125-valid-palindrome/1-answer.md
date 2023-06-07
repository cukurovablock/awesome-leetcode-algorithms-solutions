# [✅ Lowercase Alphanumeric to solve the 🧑🏻‍💻 Valid Palindrome Problem on 🦀 Python language]()

## 🧩 Complexity

The `Solution` struct contains a public function `is_palindrome` that takes a `String` parameter `s` and returns a boolean value. The goal of the function is to determine if the given string `s` is a palindrome.

The solution first converts the string `s` to lowercase using the `to_lowercase` method, storing the result in the variable `a`. This step is necessary to perform a case-insensitive comparison.

Next, the characters of `a` are collected into a vector `b` using the `chars` method. Each character is filtered using the `retain` method, which removes whitespace and punctuation characters from `b`. This is achieved by keeping only the characters for which the closure condition `!x.is_whitespace() && !x.is_ascii_punctuation()` returns true.

To check if the string is a palindrome, a clone of `b` is created in the variable `c`. The reverse method is then used to `reverse` the order of characters in `c`.

Finally, an if statement compares the vectors `b` and `c`. If they are equal, it means that the original string `s` is a palindrome, so the function returns `true`. Otherwise, it returns `false`.

## 🔐 Code

``` RUST
impl Solution {
    pub fn is_palindrome(s: String) -> bool {
        let a = s.to_lowercase();
    let mut b = a.chars().collect::<Vec<char>>();
    b.retain(|&x| !x.is_whitespace() && !x.    is_ascii_punctuation());

    let mut c = b.clone();
    c.reverse();
    if b == c{
       return true;
    }
       return false;
    }
}
```


