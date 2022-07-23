### Write an efficient algorithm that searches for a value target in an m x n integer matrix matrix. This matrix has the following properties: Integers in each row are sorted from left to right. The first integer of each row is greater than the last integer of the previous row.
 
#### Diff: Medium


#### Example 1:

Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3

Output: true

#### Example 2:

Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13

Output: false
 

#### Constraints:

> m == matrix.length

> n == matrix[i].length

> 1 <= m, n <= 100

> -104 <= matrix[i][j], target <= 104


#### Solution:
      class Solution:
        def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
            left1 = 0
            right1 = len(matrix)-1

            while left1<=right1:
                mid1 = (left1+right1)//2

                currRow = matrix[mid1]

                if target<currRow[0]:
                    right1 = mid1-1
                elif target>currRow[-1]:
                    left1 = mid1+1
                else:
                    left2 = 0
                    right2 = len(currRow)-1

                    while left2<=right2:
                        mid2 = (left2+right2)//2

                        if target<currRow[mid2]:
                            right2 = mid2-1
                        elif target>currRow[mid2]:
                            left2 = mid2+1
                        else:
                            return True
                    return False
                    
                    
[Go To Problem](https://leetcode.com/problems/search-a-2d-matrix/)
