# Contains Duplicate on Rust language

## Complexity

First, we import the necessary library std::collections::HashSet to use the HashSet data structure.ses a constant amount of memory, regardless of the size of the input array. Next, we define a function called contains_duplicate which takes a Vec<i32> input parameter named nums and returns a bool value. Inside the function, we create a HashSet of type HashSet<i32> to keep track of numbers we have encountered so far. Then, we start a loop for each element in the nums vector. At each iteration, we check if the element is already present in the set. If it is, it means we have encountered a duplicate element, so we return true. If the element is not present in the set, we add it to the set so that we can check if the next element is a duplicate. Once the loop is completed, it means there are no duplicate elements, so we return false. This way, the contains_duplicate function checks for the presence of duplicate elements in the given number vector. You can call the function and test it with sample cases to ensure its correctness. In this example, since the number 1 appears twice in the nums vector, the output will be "true". You can create your own test cases to verify that the function works correctly.

## Code

``` Rust
use std::collections::HashSet;

impl Solution {
    fn contains_duplicate(nums: Vec<i32>) -> bool {

    

    
    let mut set:HashSet<i32> = HashSet::new();

    for i in nums {
        if set.contains(&i){
            return true;
        }
        set.insert(i);
    }
    return false;
        
      
} 
}  
```
