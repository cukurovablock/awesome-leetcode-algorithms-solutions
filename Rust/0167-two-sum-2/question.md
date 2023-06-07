# [Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

## 🚨 Problem
<!-- Explanation of problem. -->
Given a **1-indexed** array of integers `numbers` that is already **_sorted in non-decreasing order_**, find two numbers such that they add up to a specific `target` number. Let these two numbers be $numbers[index_1]$ and $numbers[index_2]$ where $1 <= index_1 < index_2 < numbers.length$.

Return _the indices of the two numbers,_ $index_1$ _and_ $index_2$_, **added by one** as an integer array_ $[index_1, index_2]$ _of length 2._

The tests are generated such that there is **exactly one solution**. You **may not** use the same element twice.

Your solution must use only constant extra space.

**Example 1:**
<!-- An example of problem. -->

>**Input:**  numbers = \[2,7,11,15\], target = 9</br> <!-- Input example. -->
**Output:**  \[1,2\]</br> <!-- Output example. -->
**Explanation:** The sum of 2 and 7 is 9. Therefore, $index_1$ = 1, $index_2$ = 2. We return \[1, 2\]. <!-- Basic explanation of example. -->

**Example 2:**
<!-- An example of problem. -->

>**Input:** numbers = \[2,3,4\], target = 6 </br> <!-- Input example. -->
**Output:** \[1,3\] </br> <!-- Output example. -->
**Explanation:** The sum of 2 and 4 is 6. Therefore $index_1$ = 1, $index_2$ = 3. We return \[1, 3\]. <!-- Basic explanation of example. -->

**Example 3:**
<!-- An example of problem. -->

>**Input:** numbers = \[\-1,0\], target = -1 </br> <!-- Input example. -->
**Output:** \[1,2\] </br> <!-- Output example. -->
**Explanation:** The sum of -1 and 0 is -1. Therefore $index_1$ = 1, $index_2$ = 2. We return \[1, 2\]. <!-- Basic explanation of example. -->

**Constraints:**
<!-- Constraints of problem. -->
- $2 <= numbers.length <= 3 * 10^4$
- $-1000 <= numbers[i] <= 1000$
- `numbers` is sorted in **non-decreasing order**.
- $-1000 <= target <= 1000$
- The tests are generated such that there is **exactly one solution**.

**Follow-up:**  
<!-- Do more! -->

## 🔐 Solutions
<!-- Solutions of problem and their links. -->

| ID  |         METHOD         |
| :-- | :--------------------: |
| 1   | [Brute Force](1-answer.md) |
