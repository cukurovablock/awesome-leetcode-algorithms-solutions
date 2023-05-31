# Intuition
First of all, i need char sequence of two strings. And then, they are not sorting by any kind of method. This method needs sorting function about how to sort character array. At the end of the process, equality check is the main operation between two array.

# Approach
The main process is that we have to split all strings. We have just only two string -> s and t. So, String to character array is completed by toCharArray() built-in method. And then check the length of character arrays. If not equal length of whole array, return false situation. And then if equal, sort each character arrays and equality check between t char array to s char array.

# Complexity
- Time complexity: O(nlogn)

- Space complexity: O(n)

# Code
```java
class Solution {
    public boolean isAnagram(String s, String t) {
        char[] tmpS = s.toCharArray();
        char[] tmpT = t.toCharArray();
        if(tmpS.length != tmpT.length) {
            return false;
        }
        Arrays.sort(tmpS);
        Arrays.sort(tmpT);
        return Arrays.equals(tmpS,tmpT);
    }
}
```