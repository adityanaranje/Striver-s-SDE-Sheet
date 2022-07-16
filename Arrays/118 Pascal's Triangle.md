### Given an integer numRows, return the first numRows of Pascal's triangle. In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:

<img src="https://github.com/adityanaranje/Striver-s-SDE-Sheet/blob/main/Arrays/PascalTriangleAnimated.gif">
 
 #### Diff: Easy
 
 
#### Example 1:

Input: numRows = 5

Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]

#### Example 2:

Input: numRows = 1

Output: [[1]]
 

#### Constraints:

> 1 <= numRows <= 30


#### Solution:
    class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        
        result = []
        
        for i in range(numRows):
            # creating temperory list containing 1's to store row
            temp = [1]*(i+1)
            
            # changing elements from second to last second position
            for j in range(i-1):
                # i-1 previous row
                temp[j+1] = result[i-1][j]+result[i-1][j+1]
            result.append(temp)
        
        return result
        
        
[Go To Problem](https://leetcode.com/problems/pascals-triangle/)
