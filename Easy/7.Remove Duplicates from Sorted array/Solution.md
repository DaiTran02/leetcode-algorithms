# Remove Duplicates from sorted array
Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in nums.

Consider the number of unique elements of nums to be k, to get accepted, you need to do the following things:

Change the array nums such that the first k elements of nums contain the unique elements in the order they were present in nums initially. The remaining elements of nums are not important as well as the size of nums.
Return k.

## Solution
1. Arrange array into increasing direction
2. Check the current element with an element based on j variable if it is different, then change the current element with an element with position j.

### Complexity
1. Sort O(n log n)
2. Browse through array to eliminate duplication: O(n)

#### Code 
		public int removeDuplicates(int[] nums) {
		Arrays.sort(nums);
		int j = 0;
		for(int i = 0; i < nums.length;i++) {
			if(nums[i] != nums[j]) {
				nums[j] = nums[i];
				j++;
			}
		}
		return j;
	}