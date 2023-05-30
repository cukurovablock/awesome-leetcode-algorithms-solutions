# [1. Two Sum](https://leetcode.com/problems/two-sum)

## Problem

Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

**Example 1:**

>**Input:** nums = \[2,7,11,15\], target = 9 </br>
**Output:** \[0,1\] </br>
**Explanation:** Because nums\[0\] + nums\[1\] == 9, we return \[0, 1\].

**Example 2:**

>**Input:** nums = \[3,2,4\], target = 6 </br>
**Output:** \[1,2\]

**Example 3:**

>**Input:** nums = \[3,3\], target = 6 </br>
**Output:** \[0,1\]

**Constraints:**

- $2 <= nums.length <= 10^4$
- $-10^9 <= nums[i] <= 10^9$
- $-10^9 <= target <= 10^9$
- **Only one valid answer exists.**

**Follow-up:** Can you come up with an algorithm that is less than $O(n^2)$ time complexity?

## Solutions

| ID  |   METHOD    | LINK                               |
| :-- | :---------: | :--------------------------------- |
| 1   | Brute Force | [two-sum.md](two-sum.md)           |
| 2   | Hash Table  | [two-sum-hash.md](two-sum-hash.md) |
