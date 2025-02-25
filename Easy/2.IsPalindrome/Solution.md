# Palindrome Number

Given an integer x, return true if x is a palindrome, and false otherwise.

Example 1:
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.

Example 2:

Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.

# Solution 

1. I convert nums to String
2. Give 1 loop starting from the end of string to the top
3. I put each character in a new string when the loop starts
4. I will eventully convert that string to int and compare with x

	public int[] twoSum(int[] nums, int target) {
		int[] a = {};
		
		for(int i = 0; i < nums.length ; i++) {
			for(int j = i + 1 ; j < nums.length ; j++) {
				if(nums[i] + nums[j] == target) {
					return new int[] {i,j};
				}
			}
		}
		return a;
	}

