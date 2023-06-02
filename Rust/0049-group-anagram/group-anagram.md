# ✅ Counts the Frequencies to solve the 🧑🏻‍💻 Group Anagram Problem on 😎 Rust language


## Complexity

This code contains a function called `group_anagrams`, which takes a `Vec<String>` parameter named `strs` and returns a vector containing the groups of anagrams.

Firstly, a `HashMap` named `groups` is created. This `HashMap` will be used to group the anagrams. The keys are `Vec<char>` that represent the sorted characters of the words in alphabetical order. The values are `Vec<String>` that hold the lists of grouped words.

Then, for each word in the `strs` vector, the following steps are performed:

Convert the characters of the word into a `Vec<char>` called `chars` using the `chars()` method and `collect()` function.
Sort the `chars` vector in alphabetical order using the `sort()` method.
In the `groups` hashmap, try to find the corresponding entry using `chars` as the key. If the entry exists, the `entry` variable will hold a reference to the existing entry. If the entry doesn't exist, the `or_insert(Vec::new())` method will create a new entry with an empty `Vec<String>` as the value and return a reference to the newly created entry.
Append the word to the value associated with the obtained entry reference using the `entry.push(i)` statement. This adds the word to the value of the corresponding key, grouping the anagrams together.
Finally, the code returns a `Vec<Vec<String>>` by cloning the values from the `groups` hashmap using `groups.values().cloned().`

This way, the `group_anagrams` function will group the anagrams in the strs vector and return a vector containing the groups of anagrams.

## Code

``` Rust
use std::collections::HashMap;

impl Solution {
    pub fn group_anagrams(strs: Vec<String>) -> Vec<Vec<String>> {

        let mut groups: HashMap<Vec<char>, Vec<String>> = HashMap::new();

    for i in strs {
        let mut chars: Vec<char> = i.chars().collect();
        chars.sort();
        let entry = groups.entry(chars).or_insert(Vec::new());
        entry.push(i);
    }

    groups.values().cloned().collect()
        
    }
}
```