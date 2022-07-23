### Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.

#### Diff: Medium


#### Example 1:

Input: nums = [3,2,3]

Output: [3]

#### Example 2:

Input: nums = [1]

Output: [1]

#### Example 3:

Input: nums = [1,2]

Output: [1,2]
 

#### Constraints:

> 1 <= nums.length <= 5 * 104

> -109 <= nums[i] <= 109

#### Solution:
        class Solution:
          def majorityElement(self, nums: List[int]) -> List[int]:

              n = len(nums)
              if n<=2:
                  return list(set(nums))

              x = len(nums)//3
              res = []

              for i in range(n):
                  if nums[i] in res:
                      continue
                  else:
                      cnt = nums.count(nums[i])  # counting number count
                      if cnt>x:
                          res.append(nums[i])  # add to result if greater than 1/3

              return res
              
          
 [Go To Problem](https://leetcode.com/problems/majority-element-ii/)
