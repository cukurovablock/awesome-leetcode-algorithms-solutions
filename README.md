# Awesome Leetcode Algorithms Solututions

| Language   | Repo Link                          | Contributors                                         |
| ---------- | ---------------------------------- | ---------------------------------------------------- |
| Python     | [Pyhton](Python/README.md)         | [@muffafa](https://github.com/muffafa)               |
| Java       | [JAVA](Java/README.md)             | [@cagridemirtash](https://github.com/cagridemirtash) |
| Javascript | [Javascript](Javascript/README.md) | [@kaanncavdar](https://github.com/kaanncavdar)       |
| Rust       | [Rust](Rust/README.md)             | [@sektor7k](https://github.com/sektor7k)             |
| C++        | [Cpp](Cpp/README.md)               | [@sametaydinq](https://github.com/sametaydinq)       |

## Introduction

Welcome to the solutions of leetcode algorithms.

## How to Use It?

I suggest cloning the repository locally to work with it, but you can easily look at any solution you want without cloning it. Simply press `Ctrl + F` and type the name of the question or its ID. Each folder includes an .md file that you can click on to go to the Leetcode website. There are two parts of questions:

1. Problem: </br> This part includes the definition of the problem, example cases, input and output examples, constraints, and follow-up information.
2. Solution: </br> This part includes a table to navigate to the solutions.

## Solutions

Each .md file for a solution includes:

- Header (that navigates to the online explanation of the solution)
- Approach (describing the approach to solving the problem)
- Complexity (determining the time and space complexity of the solution)
- Code (the actual solution to the problem)

## How to Clone It?

> `git clone https://github.com/cukurovablock/awesome-leetcode-algorithms-solutions.git`

## Extensions

- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- [Markdown Table](https://marketplace.visualstudio.com/items?itemName=TakumiI.markdowntable)
- [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- [Markdown Preview Github Styling](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles)
- [Auto-Open Markdown Preview](https://marketplace.visualstudio.com/items?itemName=hnw.vscode-auto-open-markdown-preview)
- [vscode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)

## How to Contribute?

You can create a custom snippet for .md files in Visual Studio Code:

1. Open Visual Studio Code, click "File" > "Preferences" > "User Snippets".
2. Select "Markdown" from the list of languages.
3. Add the following code to create a basic markdown snippet.
4. You can easily type `mdproblem` to create a problem template and `mdsolution` to create a solution template.
5. Now you can easily start contributing!

``` json
{
 "Leetcode Problem Template": {
  "prefix": "mdproblem",
  "body": [
   "# [${6:Header}](${7:Link})",
   "",
   "## 🚨 Problem",
   "<!-- Explanation of problem. -->",
   "${1:Explain the problem}",
   "",
   "**Example 1:**",
   "<!-- An example of problem. -->",
   "",
   ">**Input:** ${2} </br> <!-- Input example. -->",
   "**Output:** ${3} </br> <!-- Output example. -->",
   "**Explanation:** ${4} <!-- Basic explanation of example. -->",
   "",
   "**Constraints:**",
   "<!-- Constraints of problem. -->",
   "- ${5}",
   "",
   "**Follow-up:**  ",
   "<!-- Do more! -->",
   "",
   "## 🔐 Solutions",
   "<!-- Solutions of problem and their links. -->",
   "",
   "| ID  | METHOD  | LINK           |",
   "| :-- | :-----: | :------------- |",
   "| 1   | example | [answer](link) |",
   ""
  ],
  "description": "It creates a problem template for leetcode"
 },
 "Leetcode Solution Template": {
  "prefix": "mdsolution",
  "body": [
   "# [${5:Header}](${6:link})",
   "",
   "## 🧑🏻‍💻 Approach",
   "<!-- Describe your approach to solving the problem. -->",
   "${1:Explain the approach}",
   "",
   "## 🔐 Code",
   "",
   "``` c",
   "${4:printf(\"Hello World\");}",
   "```",
   "## 🧩 Complexity",
   "",
   "- Time complexity:",
   "<!-- Add your time complexity here, e.g. \\$O(n)$ -->",
   "${2:Time Complexity}",
   "",
   "- Space complexity:",
   "<!-- Add your space complexity here, e.g. \\$O(n)$ -->",
   "${3:Space Complexity}",
   ""
  ],
  "description": "It creates a solution template for leetcode problem"
 },
 "Leetcode Example Template": {
  "prefix": "mdexample",
  "body": [
   "**Example ${1}:**",
   "<!-- An example of problem. -->",
   "",
   ">**Input:** ${2} </br> <!-- Input example. -->",
   "**Output:** ${3} </br> <!-- Output example. -->",
  ],
  "description": "It creates a example template for leetcode problem"
 }
}
```
