### Given an array of integers A and an integer B. Find the total number of subarrays having bitwise XOR of all elements equals to B.


#### Diff: Medium


#### Problem Constraints

> 1 <= length of the array <= 105

> 1 <= A[i], B <= 109


Input Format

The first argument given is the integer array A.

The second argument given is integer B.

Output Format

Return the total number of subarrays having bitwise XOR equals to B.


Example Input

Input 1:

A = [4, 2, 2, 6, 4]
B = 6

Input 2:

A = [5, 6, 7, 8, 9]
B = 5

Example Output

Output 1: 4

Output 2: 2



#### Solution:
        class Solution:
          # @param A : list of integers
          # @param B : integer
          # @return an integer
          def solve(self, A, B):

              count = 0

              hashmap = {}
              hashmap[0] = 1
              xor = 0
              for i in range(len(A)):
                  xor ^= A[i]
                  if xor ^ B in hashmap:
                      count += hashmap[xor^B]

                  if xor not in hashmap:
                      hashmap[xor] = 0
                  hashmap[xor] += 1

              return count
       
[Go To Problem](https://www.interviewbit.com/problems/subarray-with-given-xor/)
