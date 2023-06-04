# [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

## 🚨 Problem
<!-- Explanation of problem. -->
Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
3. Every close bracket has a corresponding open bracket of the same type.

**Example 1:**
<!-- An example of problem. -->

>**Input:** s = "()" </br> <!-- Input example. -->
**Output:** true </br> <!-- Output example. -->

**Example 2:**
<!-- An example of problem. -->

>**Input:** s = "()\[\]{}" </br> <!-- Input example. -->
**Output:** true </br> <!-- Output example. -->

**Example 3:**
<!-- An example of problem. -->

>**Input:** s = "(\]" </br> <!-- Input example. -->
**Output:** false </br> <!-- Output example. -->

**Constraints:**
<!-- Constraints of problem. -->
- $1 <= s.length <= 10^4$
- `s` consists of parentheses only `'()[]{}'`.

## 🔐 Solutions
<!-- Solutions of problem and their links. -->

| ID  |         METHOD         |
| :-- | :--------------------: |
| 1   | [Stack and Map](1-answer.md) |
