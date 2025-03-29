# Remove Element 
Given an integer array nums and an integer val, remove all occurrences of val in nums in-place. The order of the elements may be changed. Then return the number of elements in nums which are not equal to val.

Consider the number of elements in nums which are not equal to val be k, to get accepted, you need to do the following things:

Change the array nums such that the first k elements of nums contain the elements which are not equal to val. The remaining elements of nums are not important as well as the size of nums.
Return k.

# Solution
1. Create a variable k to save postion.
2. Browse the array and check to see which element is not the same as the val, then update the position for that element 

### Complexity
Browse the array => O(n)

#### Code 
	 public int removeElement(int[] nums, int val) {
        int k = 0;
		for(int i = 0; i < nums.length ; i++) {
			if(nums[i] != val) {
				nums[k] = nums[i];
				k++;
			}
		}
		return k;
    }