### A permutation of an array of integers is an arrangement of its members into a sequence or linear order. For example, for arr = [1,2,3], the following are considered permutations of arr: [1,2,3], [1,3,2], [3,1,2], [2,3,1]. The next permutation of an array of integers is the next lexicographically greater permutation of its integer. More formally, if all the permutations of the array are sorted in one container according to their lexicographical order, then the next permutation of that array is the permutation that follows it in the sorted container. 
### If such arrangement is not possible, the array must be rearranged as the lowest possible order (i.e., sorted in ascending order).
### For example, the next permutation of arr = [1,2,3] is [1,3,2].
### Similarly, the next permutation of arr = [2,3,1] is [3,1,2].
### While the next permutation of arr = [3,2,1] is [1,2,3] because [3,2,1] does not have a lexicographical larger rearrangement. Given an array of integers nums, find the next permutation of nums.

### The replacement must be in place and use only constant extra memory.

#### Diff: Medium 

#### Example 1:

Input: nums = [1,2,3]

Output: [1,3,2]


#### Example 2:

Input: nums = [3,2,1]

Output: [1,2,3]


#### Example 3:

Input: nums = [1,1,5]

Output: [1,5,1]
 

#### Constraints:

> 1 <= nums.length <= 100

> 0 <= nums[i] <= 100


#### Solution:
    class Solution:
    def nextPermutation(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        length = len(nums)
        # if elments are less than 2
        if length<=2:
            return nums.reverse()
        
        pointer = length - 2
        
        # start from last element and traverse while we reach end or follow ascending pattern from right-left
        
        while pointer >= 0 and (nums[pointer] >= nums[pointer+1]):
            pointer -=1
            
        # if pointer becomes -1 that means we reach last permutations so we return the first permutaitons which is reverse of last one    
        if pointer==-1:
            return nums.reverse()
        
        # swapping last element greater than pointer element
        for i in range(length-1, pointer, -1):
            if nums[pointer] < nums[i]:
                nums[pointer], nums[i] = nums[i], nums[pointer]
                break
        
        # reversing elements just after pointer
        nums[pointer+1:] = reversed(nums[pointer+1:])
        
        
 [Go to Problem](https://leetcode.com/problems/next-permutation/)
