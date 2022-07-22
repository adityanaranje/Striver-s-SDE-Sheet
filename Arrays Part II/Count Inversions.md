### For a given integer array/list 'ARR' of size 'N' containing all distinct values, find the total number of 'Inversions' that may exist. An inversion is defined for a pair of integers in the array/list when the following two conditions are met.
### A pair ('ARR[i]', 'ARR[j]') is said to be an inversion when:

> 1. 'ARR[i] > 'ARR[j]' 

> 2. 'i' < 'j'

### Where 'i' and 'j' denote the indices ranging from [0, 'N').


#### Input Format :
#### The first line of input contains an integer 'N', denoting the size of the array.

#### The second line of input contains 'N' integers separated by a single space, denoting the elements of the array 'ARR'.

#### Output Format :
#### Print a single line containing a single integer that denotes the total count of inversions in the input array.

Note:
You are not required to print anything, it has been already taken care of. Just implement the given function.  

#### Constraints :

> 1 <= N <= 10^5 

> 1 <= ARR[i] <= 10^9

> Where 'ARR[i]' denotes the array element at 'ith' index.

Time Limit: 1 sec

##### Sample Input 1 :
3
3 2 1
##### Sample Output 1 :
3

Explanation Of Sample Output 1:
We have a total of 3 pairs which satisfy the condition of inversion. (3, 2), (2, 1) and (3, 1).

##### Sample Input 2 :
5
2 5 1 3 4
##### Sample Output 2 :
4
Explanation Of Sample Output 1:
We have a total of 4 pairs which satisfy the condition of inversion. (2, 1), (5, 1), (5, 3) and (5, 4).


#### Solution:
      from os import *
      from sys import *
      from collections import *
      from math import *    


      def mergeSort(arr, temp_arr, left, right):
          inv_count = 0

          if left< right:
              mid = (right+left)//2

              inv_count += mergeSort(arr, temp_arr, left, mid)
              inv_count += mergeSort(arr, temp_arr, mid+1, right)
              inv_count += merge(arr, temp_arr, left, mid, right)
          return inv_count 

      def merge(arr, temp_arr, left, mid, right):
          i = left
          j = mid+1
          k = left
          inv_count = 0


          while i<=mid and j<=right:
              if arr[i]<=arr[j]:
                  temp_arr[k] = arr[i]
                  i +=1
                  k+=1
              else:
                  temp_arr[k] = arr[j]
                  j +=1
                  k +=1
                  inv_count += (mid-i)+1

          while i<=mid:
              temp_arr[k] = arr[i]
              k+=1
              i+=1
          while j<=right:
              temp_arr[k] = arr[j]
              k+=1
              j+=1

          for x in range(left, right+1):
              arr[x] = temp_arr[x]

          return inv_count

      def getInversions(arr, n) : 
          temp_arr = [0]*n
          return mergeSort(arr, temp_arr, 0, n-1)

      # Taking inpit using fast I/O.
      def takeInput() :
          n = int(input())
          arr = list(map(int, stdin.readline().strip().split(" ")))
          return arr, n 

      # Main.
      arr, n = takeInput()
      print(getInversions(arr, n))
      
      
      
      
[Go To Problem](https://www.codingninjas.com/codestudio/problems/615?topList=striver-sde-sheet-problems&utm_source=striver&utm_medium=website&leftPanelTab=0)
