# [✅ Stack and Map to solve the 🧑🏻‍💻 Valid Parentheses on 🦀  RUST language]()

## 🧑🏻‍💻 Approach

Create an empty vector called `result` to act as a stack.

Iterate over each character, `i`, in the given string `s`.

Inside the loop, use a match statement to handle different cases:

If i is an opening bracket, i.e., `'('`, `'{'`, or `'['`, push it onto the stack (`result` vector).

If `i` is a closing bracket, check if the top element of the stack matches the corresponding opening bracket. If it does not match or the stack is empty, return `false`, as the brackets are not valid.

After processing all the characters, check if the stack is empty. If it is empty, return `true`, indicating that all brackets are valid. Otherwise, return `false`, indicating that there are unmatched brackets.

## 🔐 Code

``` RUST
impl Solution {
    pub fn is_valid(s: String) -> bool {

    let mut result : Vec<char> = Vec::new();

    for i in s.chars(){
        match i {
            '('|'{'|'[' => result.push(i),
            ')' => {
                if result.pop() != Some('('){
                    return false;
                }
            }
            '}' => {
                if result.pop() != Some('{'){
                    return false;
                }
            }
            ']' => {
                if result.pop() != Some('['){
                    return false;
                }
            }
            
            _ => return false,
        }
        
        
    }
    return result.is_empty();
      
        
 }

}
```


