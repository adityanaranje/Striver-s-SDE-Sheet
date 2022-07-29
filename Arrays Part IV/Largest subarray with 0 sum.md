### Given an array having both positive and negative integers. The task is to compute the length of the largest subarray with sum 0.

#### Diff:Easy

#### Example 1:

Input:

N = 8

A[] = {15,-2,2,-8,1,7,10,23}

Output: 5

Explanation: The largest subarray with sum 0 will be -2 2 -8 1 7.

Your Task:
You just have to complete the function maxLen() which takes two arguments an array A and n, where n is the size of the array A and returns the length of the largest subarray with 0 sum.

Expected Time Complexity: O(N).
Expected Auxiliary Space: O(N).

#### Constraints:

> 1 <= N <= 105

> -1000 <= A[i] <= 1000, for each valid i

#### Solution:
        class Solution:
            def maxLen(self, n, arr):
                #Code here

                hash_map = {}
                long_arr = 0
                curr_sum = 0

                for i in range(n):
                    curr_sum += arr[i]

                    if arr[i] is 0 and long_arr is 0:
                        long_arr = 1
                    if curr_sum is 0:
                        long_arr = i+1

                    if curr_sum in hash_map:
                        long_arr = max(long_arr, i-hash_map[curr_sum])
                    else:
                        hash_map[curr_sum] = i

                return long_arr


[Go To Problem](https://practice.geeksforgeeks.org/problems/largest-subarray-with-0-sum/1)
