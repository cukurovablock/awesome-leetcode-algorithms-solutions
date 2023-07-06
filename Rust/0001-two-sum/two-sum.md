# Brute Force to solve the Two-Sum Problem on Rust language


## 🧑🏻‍💻 Approach

The function `two_sum` takes two parameters: a vector of integers `nums` and a target integer `target`. It aims to find two numbers in the `nums` vector whose sum equals the `target`. The function returns a vector containing the indices of these two numbers.

In the beginning, you initialize an empty vector called `result` to store the indices of the two numbers.

You then iterate through the `nums` vector using two nested loops, represented by `i` and `j`. The condition `i.0 != j.0` ensures that you don't compare the same element with itself.

Inside the nested loops, you check if the sum of the current pair of numbers (`i.1` and `j.1`) is equal to the `target`. If it is, you push the indices (`i.0` and `j.0`) into the `result` vector and break out of the inner loop.

After the inner loop, you check if the `result` vector contains any indices. If it does, you break out of the outer loop as well.

Finally, you return the `result` vector.
## Code

``` Rust
impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {

        let mut result = Vec::new();
        
    for i in nums.iter().enumerate(){


    for j in nums.iter().enumerate(){

        if i.0 != j.0 && i.1+j.1== target{

          result.push(i.0 as i32);
          result.push(j.0 as i32);
          break;
          
        }
    }
    if result.len()>0{
      break;
    }
  }
  return result;

    
    }
}  
```
