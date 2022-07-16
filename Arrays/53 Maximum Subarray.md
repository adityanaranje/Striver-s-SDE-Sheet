### Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum. A subarray is a contiguous part of an array.


#### Diff: Medium


#### Example 1:

Input: nums = [-2,1,-3,4,-1,2,1,-5,4]

Output: 6

Explanation: [4,-1,2,1] has the largest sum = 6.


#### Example 2:

Input: nums = [1]

Output: 1


#### Example 3:

Input: nums = [5,4,-1,7,8]
Output: 23
 

#### Constraints:

> 1 <= nums.length <= 105
> -104 <= nums[i] <= 104


#### Solution:
    class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        
        
        maxSub = nums[0]
        # initialize sum as 0
        currSum = 0
        
        
        for i in nums:
            # if sum becoms negative make it 0
            if currSum<0:
                currSum = 0
            
            # add current element to sum
            currSum+=i
            # get maximum of current sum and previous maximum sum
            maxSub = max(maxSub, currSum)
            
        return maxSub
        
[Go To Problem](https://leetcode.com/problems/maximum-subarray/)
