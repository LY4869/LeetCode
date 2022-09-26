Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.

# Example
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

# Solution
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {

        // map<value, index>
        unordered_map<int, int> m;

        int size = nums.size();
        for(int i = 0; i < size; i++)
        {
			// Return specific index if find target
            if(m.find(target - nums[i]) != m.end())
                return {m[target - nums[i]], i};

			// Insert value to map if not find target
            m[nums[i]] = i;
        }
		// Return {-1, -1} if don't have solution
        return {-1, -1};
    }
};
```