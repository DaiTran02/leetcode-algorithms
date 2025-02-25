# Two sum
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target
## Example 1:
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Becouse nums[0] + nums[1] == 9, we return [0,1]

- How I solve it.
1. I give 1 loop from 0 to number of nums
2. I continue to repeat one more time from i + 1 to the number of nums
3. Then I will find from the pair together so that the pair of given by Target

- Complexity
- Time complexity : O(n^2) Two cage loops
- Space Complexity: O(1)
## Code
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

# Solution 2: HashMap (O(n))
1. Use a HashMap to store visited elements and their indices
2. For each nums[i], check if target - nums[i] exists in the map
3. If yes, return the indices [map.get(target - nums[i]),i].
4. Otherwise, store nums[i] in the map.

	public int[] twoSum(int[] nums, int targer){
		Map<Integer> map = new HashMap<>();

		for(int i = 0; i < nums.leghth ; i++){
			int check = nums[i] - target;
			if(map.containKey(check)){
				return new int[] (map.get(check),i); 
			}
			map.put(nums[i],i);
		}
		return new int[] {};
	}
