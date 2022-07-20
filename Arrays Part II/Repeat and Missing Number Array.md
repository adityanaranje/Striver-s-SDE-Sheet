### You are given a read only array of n integers from 1 to n. Each integer appears exactly once except A which appears twice and B which is missing. Return A and B. Note: Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

#### Note that in your output A should precede B.

#### Example:

Input:[3 1 2 5 3] 

Output:[3, 4] 

A = 3, B = 4


Solution:

      class Solution:
    # @param A : tuple of integers
    # @return a list of integers
    def repeatedNumber(self, A):
        lst = []
        # sum of all elements
        sum1 = sum(A)
        
        # sum of all elements except the duplicate one
        sum2 = sum(list(set(A)))
        
        
        n = len(A)
        
        # sum of all n elements
        b = n*(n+1)//2
        
        # get duplicate element
        lst.append(sum1-sum2)
        
        # get missing element as subtracting from sum of all elements
        lst.append(b-sum2)
        
        return lst
        
[Go To Problem](https://www.interviewbit.com/problems/repeat-and-missing-number-array/)
