### Given the head of a singly linked list, reverse the list, and return the reversed list.

#### Diff: Easy 


#### Example 1:

Input: head = [1,2,3,4,5]

Output: [5,4,3,2,1]

#### Example 2:

Input: head = [1,2]

Output: [2,1]

#### Example 3:

Input: head = []

Output: [] 

#### Constraints:

> The number of nodes in the list is the range [0, 5000].

> -5000 <= Node.val <= 5000


#### Solution:
            # Definition for singly-linked list.
            # class ListNode:
            #     def __init__(self, val=0, next=None):
            #         self.val = val
            #         self.next = next
            class Solution:
                def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:

                    newList = None

                    while head:
                        temp = head.next
                        head.next = newList
                        newList = head
                        head = temp

                    return newList
                    
                    
[Go To Problem](https://leetcode.com/problems/reverse-linked-list/)
