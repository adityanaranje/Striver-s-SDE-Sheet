### Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's.
### You must do it in place.

#### Diff: Medium

#### Example 1:
Input: matrix = [[1,1,1],[1,0,1],[1,1,1]]

Output: [[1,0,1],[0,0,0],[1,0,1]]


#### Example 2:
Input: matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]

Output: [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
 

#### Constraints:

> m == matrix.length

> n == matrix[0].length

> 1 <= m, n <= 200

> -231 <= matrix[i][j] <= 231 - 1
 

#### Follow up:
A straightforward solution using O(mn) space is probably a bad idea.
A simple improvement uses O(m + n) space, but still not the best solution.
Could you devise a constant space solution?


#### Solution:


    class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        r = len(matrix)   # no of rows
        c = len(matrix[0]) # no of columns
        
        # create a list to store row no
        rows = [0]*r  
        # create a list to store column no
        cols = [0]*c  
        
        
        # get row no. and column no. which are set to be 0
        for i in range(r):
            for j in range(c):
                if matrix[i][j]==0:
                    rows[i] = 1
                    cols[j] = 1
                    
        # setting rows as 0            
        for i in range(r):
            if rows[i]==1:
                for l in range(c):
                    matrix[i][l] = 0
                    
        # setting cols as 0            
        for i in range(c):
            if cols[i]==1:
                for l in range(r):
                    matrix[l][i] = 0
