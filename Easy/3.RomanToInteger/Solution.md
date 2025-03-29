# Roman to Integer
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
For example, 2 is written as II in Roman numeral, just two ones added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

I can be placed before V (5) and X (10) to make 4 and 9. 
X can be placed before L (50) and C (100) to make 40 and 90. 
C can be placed before D (500) and M (1000) to make 400 and 900.
Given a roman numeral, convert it to an integer.

 

Example 1:

Input: s = "III"
Output: 3
Explanation: III = 3.
Example 2:

Input: s = "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.

# Solution
1. I create a map to save Roman's key and value 
2. Then give a loop from 0 to the size of that string
3. Then I checked if the value of the current number is smaller than the next number, I take the current result minus the current number.

# Complexity Analysis of RomanToInteger
Time Comlexity
- The function interates through the string x once using a for loop, meaning the number of iterations is n (where n = x.length()).
- In each interation:
+ HashMap lookup (map.get(x.charAt(i))) -> O(1)
+ Comparison (map.get(x.charAt(i)) < map.get(charAt(i+1))) -> O(1)
+ Addition/Subtraction (result += ... or result -= ...) -> O(1)
=> Overall time complexity: O(n) x O(1) = O(n) 
=> Time Complexity O(n) Interates through the string once

- Space Complexity
+ The HashMap stores a fixed set of 7 key-value pairs (I, V, X, L, C, D, M), which does net depend on the input size -> O(1).
+ The function uses a few Integer variables (result,i) -> O(1).
+ No additional data structures (like arrays or lists) that depend on n are created.
=> Overall Space Complexity: O(1)

Space Complexity O(1) Uses a fixed-side HashMap and a few variables