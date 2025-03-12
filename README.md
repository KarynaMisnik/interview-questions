# interview-questions

Menu:
[Two Sum Problem](#two-sum-problem)
[Valid Anagram](#valid-anagram)

## Two Sum Problem

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

<code>function twoSum(nums, target) {
    let map = {}; 
    for (let i = 0; i < nums.length; i++) {
        let complement = target - nums[i]; 
        if (map[complement] !== undefined) {
            return [map[complement], i]; 
        }
        map[nums[i]] = i;
    }
    return []; 
    }
</code>

## Valid Anagram

Problem:
Given two strings, s and t, determine if t is an anagram of s.
An anagram is a word or phrase formed by rearranging the letters of a different word or phrase, using all the original letters exactly once.

<code>Input: s = "listen", t = "silent"  
Output: True
</code>


Constraints:

> Both s and t consist of lowercase English letters.
> The lengths of s and t can be different.

Solution:

<code>
function isAnagram(s, t) {
    if (s.length !== t.length) return false;
    return s.split('').sort().join('') === t.split('').sort().join('');
}
</code>

 Bonus: O(n) time complexity 

<code>function isAnagram(s, t) {
    if (s.length !== t.length) return false; 
    let count = {}; 
    for (let char of s) {
        count[char] = (count[char] || 0) + 1;
    }
    for (let char of t) {
        if (!count[char]) return false; 
        count[char]--; 
    }
    return true; 
}
</code>
















