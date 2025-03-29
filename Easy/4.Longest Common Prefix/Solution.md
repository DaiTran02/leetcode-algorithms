# Longest Common Prefix
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

 

Example 1:

Input: strs = ["flower","flow","flight"]
Output: "fl"
Example 2:

Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.

## Solution
1. First I will arrange it by alphabet
2. Create two string variables are first and last
3. Next I take the first value and the last value in the array 
4. Then I compare from the character of each value with the While loop
5. Check the characters of fist and of last, if the same, increase the value of the index otherwise break it.
6. Then return the value from 0 to index of first variable

### Code
	public String longestCommonPrefix(String[] strs) {
		Arrays.sort(strs);

		String first = strs[0];
		String last = strs[strs.length -1];
		
		int index = 0;
		while(index < first.length() && index < last.length()) {
			if(first.charAt(index) == last.charAt(index)) {
				index++;
			}else {
				break;
			}
		}
		
		return first.substring(0,index);
	}



