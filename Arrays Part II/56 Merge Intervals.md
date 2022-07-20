### Given an array of intervals where intervals[i] = [starti, endi], merge all overlapping intervals, and return an array of the non-overlapping intervals that cover all the intervals in the input.

#### Diff: Medium


#### Example 1:

Input: intervals = [[1,3],[2,6],[8,10],[15,18]]

Output: [[1,6],[8,10],[15,18]]

Explanation: Since intervals [1,3] and [2,6] overlap, merge them into [1,6].

#### Example 2:

Input: intervals = [[1,4],[4,5]]

Output: [[1,5]]

Explanation: Intervals [1,4] and [4,5] are considered overlapping.
 

#### Constraints:

> 1 <= intervals.length <= 104

> intervals[i].length == 2

> 0 <= starti <= endi <= 104

#### Solution:

      class Solution:
          def merge(self, intervals: List[List[int]]) -> List[List[int]]:

              intervals.sort()

              # add first element
              lst = [intervals[0]]

              for i in range(1, len(intervals)):
                  # if last element is greater than first element of further
                  # update the interval

                  if lst[-1][1]>=intervals[i][0]:
                      lst[-1][1] = max(lst[-1][1], intervals[i][1])
                  else:
                      lst.append(intervals[i])
              return lst
              
 [Go To Problem](https://leetcode.com/problems/merge-intervals/)
