# [✅ Prefix and Postfix to solve the 🧑🏻‍💻 Product of Array Except Self Problem on 🦀 Rust language]()

## 🧩 Complexity

First, we assign the length of the `nums` vector to the variable `n`.

We create a vector called `left_vecs` and initialize each element to 1. This vector will represent the prefix products of each element.

Next, we create a variable called `left` and set its initial value to 1. This variable will represent the product on the left side of each element.

Using a loop from 1 to `n`, we update the `left` value and populate the `left_vecs` vector. At each step, we multiply `left` with the previous element in `nums` and assign the result to the corresponding index in `left_vecs`.

We create a variable called `right` and set its initial value to 1. This variable will represent the product on the right side of each element.

We create a result vector called `result` and initialize each element to 0.

Using a reverse loop from `n-1` to 0, we fill the `result` vector. At each step, we multiply the prefix product (`left_vecs[i]`) with the suffix product (`right`) and assign the `result` to the corresponding index in `result`. Then, we update the right value by multiplying it with the current element in `nums`.

Finally, we return the `result` vector.


## 🔐 Code

``` RUST
impl Solution {
    pub fn product_except_self(nums: Vec<i32>) -> Vec<i32> {
        
    let n = nums.len();

    // prefix
    let mut left_vecs = vec![1;n];
    let mut left = 1;

    for i in 1..n{
        left *= nums[i-1];
        left_vecs[i] = left
    }

    // spefix or result
    let mut right = 1;
    let mut result = vec![0;n];
    for i in (0..n).rev(){
        result[i] = left_vecs[i] * right;
        right *= nums[i];
    }


    return result;
    }
}    
```

