# [✅ Counts the Frequencies to solve the 🧑🏻‍💻 Binary Search Problem on 🦀 Rust language]()

## 🧑🏻‍💻 Approach
The function `search` takes in a vector of integers (`nums`) and a target integer (`target`).
A copy of the `nums` vector is created and stored in `nums2` to avoid modifying the original vector.
The `nums2` vector is sorted in ascending order using the `sort()` function.
Pointers `low` and `high` are initialized to keep track of the search range in the sorted vector.
The binary search algorithm is performed using a while loop, which continues until `low` is greater than `high`.
Inside the loop, the middle index `mid` is calculated as the average of `low` and `high`.
The element at the middle index (`nums2[mid]`) is compared to the target.
If they are equal, it means the target has been found, and the index `mid` is returned as the result.
If the element at the middle index is less than the target, it means the target is in the right half of the remaining range. Therefore, the `low` pointer is moved to `mid + 1`.
If the element at the middle index is greater than the target, it means the target is in the left half of the remaining range. Therefore, the `high` pointer is moved to `mid - 1`.
If the target is not found after the loop finishes, `-1` is returned as the result.

## 🔐 Code

``` rust
    impl Solution {
    pub fn search(nums: Vec<i32>, target: i32) -> i32 {
        let mut nums2 = nums.clone();
    nums2.sort();

    let mut low = 0;
    let mut high = nums2.len() as i32 - 1;

    while low <= high{
        let mid= (low+(high - low)/2) as usize;
        if nums2[mid] == target{
            return mid as i32;
        }
        else if nums2[mid]< target {
            low = mid as i32 +1;
        }
        else {
            high = mid as i32 -1
        }
    }
    -1
    }
}
```
