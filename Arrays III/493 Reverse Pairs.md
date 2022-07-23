### Given an integer array nums, return the number of reverse pairs in the array.
### A reverse pair is a pair (i, j) where 0 <= i < j < nums.length and nums[i] > 2 * nums[j].


#### Diff: Hard

#### Example 1:

Input: nums = [1,3,2,3,1]

Output: 2

#### Example 2:

Input: nums = [2,4,3,5,1]

Output: 3
 
#### Constraints:

> 1 <= nums.length <= 5 * 104

> -231 <= nums[i] <= 231 - 1

#### Solution:

      def mergeSort(arr, temp, low, high):
        inv = 0
        if low>=high:
            return 0
        mid = (low+high)//2
        inv += mergeSort(arr, temp, low, mid)
        inv += mergeSort(arr, temp, mid+1, high)
        inv += merge(arr, temp, low, mid, high)

        return inv

    def merge(arr, temp, low, mid, high):

        cnt = 0
        j = mid+1
        for i in range(low, mid+1):
            while (j<=high) and (arr[i]> 2*arr[j]):
                j +=1
            cnt += j-(mid+1)

        i = low
        j = mid+1
        k = low
        while i<=mid and j<=high:
            if arr[i]<=arr[j]:
                temp[k] = arr[i]
                k+=1 
                i+=1
            else:
                temp[k] = arr[j]
                k+=1
                j+=1

        while i<=mid:
            temp[k] = arr[i]
            k+=1
            i+=1
        while j<=high:
            temp[k] = arr[j]
            k+=1
            j+=1

        for i in range(low, high+1):
            arr[i] = temp[i]
        return cnt

    class Solution:
        def reversePairs(self, nums: List[int]) -> int:
            n = len(nums)
            temp = [0]*n
            return mergeSort(nums, temp, 0, n-1)
            
            
[Go To Problem](https://leetcode.com/problems/reverse-pairs/)
