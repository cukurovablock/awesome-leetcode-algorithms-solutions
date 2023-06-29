# [✅ Counts and Sort to solve the 🧑🏻‍💻 Top K Frequent Elements Problem on 🦀 RUST language]()

## 🧑🏻‍💻 Approach

You defined a helper function called `remove_duplicates`. This function removes duplicate numbers from the given vector and returns a sorted vector. It achieves this by first converting the input vector into a `HashSet`, which automatically filters out duplicates. Then, it converts the `HashSet` back into a `Vec` and sorts it to maintain the order of the numbers.

You also defined another helper function called `sort_hashmap_by_value`. This function sorts a given `HashMap` by its values and returns a sorted vector of key-value pairs. It converts the `HashMap` into a `Vec` of `(i32, i32)` tuples and uses the `sort_by` function to sort the tuples based on their values.

The `top_k_frequent` function is the main solution function. It calculates the frequencies of numbers in the given `nums` vector and returns the first `k` numbers with the highest frequency.

Firstly, it creates an empty `HashMap` called `map` and calculates the frequencies of numbers in the `nums` vector by inserting them into the `map` with their corresponding counts.

Then, it uses the `remove_duplicates` function to remove duplicates from the `nums` vector and obtain a sorted vector called `vec`.

Next, it uses the `sort_hashmap_by_value` function to sort the `map` by its values and obtains a sorted vector called `vec3`.

Finally, it extracts the numbers with the highest frequencies from the `vec3` vector, up to the `k` specified, and adds them to the `vec2` vector.

The function returns the `vec2` vector as the result.

## 🔐 Code

``` RUST
use std::collections::{HashMap, HashSet};

impl Solution {

   pub fn top_k_frequent(nums: Vec<i32>, k: i32) -> Vec<i32> {

    fn remove_duplicates(nums: Vec<i32>) -> Vec<i32> {
        let set: HashSet<i32> = nums.into_iter().collect();
        let mut result: Vec<i32> = set.into_iter().collect();
        result.sort();
        result
    }

    fn sort_hashmap_by_value(map: HashMap<i32, i32>) -> Vec<(i32, i32)> {
        let mut vec: Vec<(i32, i32)> = map.into_iter().collect();
        vec.sort_by(|(_, value1), (_, value2)| value1.cmp(value2));
        vec
    }

    let mut map: HashMap<i32, i32> = HashMap::new();

    let vec = remove_duplicates(nums.clone());

    let mut vec2: Vec<i32> = Vec::new();

    for i in vec {
        let mut count = 0;
        for j in nums.clone() {
            if i == j {
                count += 1
            }
        }
        map.insert(i, count);
    }

    let vec3 = sort_hashmap_by_value(map);
    let mut k2 = k;

    let mut l = vec3.len() - 1;
    loop {
        if k2 == 0 {
            break;
        }
        vec2.push(vec3[l].0);
        l -= 1;
        k2 -= 1;
    }

    return vec2;
}

}
```

