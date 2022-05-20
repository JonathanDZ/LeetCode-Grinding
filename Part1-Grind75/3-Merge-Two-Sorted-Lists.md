# LeetCode Grinding Sheet 3

## Basic Information

- Start time: 2022.5.20 9:46
- Problem: Merge Two Sorted List
  - Problem Description:
- Current list: Grind 75

## Constraints

输入是两个sorted list的head，输出是merged sorted list的head

## Thinking Process

> Write down my thinking process like I'm trying to explain my ideas in the interview. If I stuck here for 15 minutes, jump to the next part.
> Be aware that:
>
> - Use readable method names, variable names;
> - Handle edge cases;
> - Don't use submit button as debugger, manual debug my code after finish it;
> - Write with good style;
> - Analyze Complexity after everything done;

创建一个新的list，创建两个指针用于记录当前需要比较的node，如果第一个list的node的value大于等于第二个list的node就把第一个指针指向的value加入到新的list当中，然后指向下一个节点，否则，把第二个指针指向的value加入到新的list当中，然后指向下一个节点。

如果一个list最终被遍历完，就直接把另一个list里的元素全部复制到新list当中就可以了。

``` python
# write my code here
class ListNode(object):
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
class Solution:
    def mergeTwoLists(self, list1, list2):
        mergedList = None
        pointer1 = list1
        pointer2 = list2
        while (pointer1 != None and pointer2 != None):
            if (pointer1.val <= pointer2.val):
                if (mergedList is None):
                    mergedList = ListNode(pointer1.val, None)
                    pointerMergedList = mergedList
                    continue
                pointerMergedList.next = ListNode(pointer1.val, None)
                pointerMergedList = pointerMergedList.next
                pointer1 = pointer1.next
            else:
                if (mergedList is None):
                    mergedList = ListNode(pointer2.val, None)
                    pointerMergedList = mergedList
                    continue
                pointerMergedList.next = ListNode(pointer2.val, None)
                pointerMergedList = pointerMergedList.next
                pointer2 = pointer2.next
        
        if (pointer1 is None):
            while (pointer2 != None):
                pointerMergedList.next = ListNode(pointer2.val, None)
                pointerMergedList = pointerMergedList.next
                pointer2 = pointer2.next
        else:
            while (pointer1 != None):
                pointerMergedList.next = ListNode(pointer1.val, None)
                pointerMergedList = pointerMergedList.next
                pointer1 = pointer1.next
        
        return mergedList
# 纠错小练习:)
```

## Test Cases

``` text
Input: [] [0]
Output: [0]

Input: [] []
Output: []
```

好像输入一个空list会导致出问题啊，这样会导致自己没有初始化参数，然后返回变量未定义的错误，这个要处理一下

## Summary

> After read the answer, fill this part.

- Time Consumed: 9:46 - 10:44
- Category of the Problem:
  - Data Structure: Linked list
  - Algorithm:
- Any code worth to record here?
  - Method Name, Variable Name:
    - Name the pointer always point at last node as "tail".
  - Useful build in method(function):
  - Algorithm implement template:
    - Use a dummy node (or sentinel node) to avoid edge case.
- Did I miss any edge case? Put it here:
- Complexity:
  - Time: O(M+N)
  - Space: O(M+N)

``` python
# Write the solution here
class Solution:
    def mergeTwoList(self, l1: ListNode, L2: ListNode) -> ListNode:
        dummy = ListNode()
        tail = dummy

        while l1 and l2:
            if l1.val < l2.val:
                tail.next = l1
                l1 = l1.next
            else:
                tail.next = l2
                l2 = l2.next
            tail = tail.next
        
        if l1:
            tail.next = l1
        elif l2:
            tail.next = l2
        
        return dummy.next
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
