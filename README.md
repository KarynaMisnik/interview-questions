# interview-questions

Two Sum Problem

Problem:
Given an array of integers nums and an integer target, return the indices of the two numbers such that they add up to target.

<code>Input: nums = [2, 7, 11, 15], target = 9  
Output: [0, 1]  # Because nums[0] + nums[1] = 2 + 7 = 9  
</code>


Solution:

<code>function twoSum(nums, target) {
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) { 
            if (nums[i] + nums[j] === target) {
                return [i, j]; // Return indices, not numbers
            }
        }
    }
    return []; 
}
</code>

Bonus: Solve it in O(n) time complexity.
