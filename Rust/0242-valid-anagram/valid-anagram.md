# ✅ Counts the Frequencies to solve the 🧑🏻‍💻 Valid Anagram Problem on 😎 Rust language

## 🧑🏻‍💻 Approach

This code contains a function `is_anagram` nested inside a structure called `Solution`. The function checks whether the given two input strings are anagrams of each other.

Here's how the function works:

First, it compares the lengths of the strings `s` and `t`. If they have different lengths, it means they cannot be anagrams, so the function returns `false`.

The function converts the strings s and t into character arrays using the `chars()` function. Then, it converts these character arrays into vectors of type `Vec<char>`. These vectors will be used to compare and sort the characters.

The function sorts the vectors `vec_s` and `vec_t`, ensuring that the characters are in the correct order for comparison.

After sorting, it compares the vectors `vec_s` and `vec_t`. If the vectors are equal, it means the input strings are anagrams of each other, and the function returns `true`.

If the vectors are not equal, it means the input strings are not anagrams, and the function returns `false`.

## Code

``` Rust
impl Solution {
    pub fn is_anagram(s: String, t: String) -> bool {
        
    if s.len() != t.len() {
        return false;
    }

    let mut vec_s = s.chars().collect::<Vec<char>>();

    let mut vec_t = t.chars().collect::<Vec<char>>();

    vec_s.sort();
    vec_t.sort();

    if vec_s == vec_t {
        return true;
    }
    
    return false;
    }
}
```