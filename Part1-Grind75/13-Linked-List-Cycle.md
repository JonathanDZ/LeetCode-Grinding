# LeetCode Grinding Sheet 13

## Basic Information

- Start time: 8:50
- Problem: Linked List Cycle
  - Problem Description:
- Current list: Grind 75

## Constraints

## Thinking Process

> Write down my thinking process like I'm trying to explain my ideas in the interview. If I stuck here for 15 minutes, jump to the next part.
> Be aware that:
>
> - Use readable method names, variable names;
> - Handle edge cases;
> - Don't use submit button as debugger, manual debug my code after finish it;
> - Write with good style;
> - Analyze Complexity after everything done;

首先怎么确定一个节点的身份？应该可以通过比较self.next所储存的地址来判断吧？

我觉得我可以储存一份所有节点地址的hashmap,然后每次都比较一下下一个节点的地址是不是已经在这个hashmap里了，如果出现了，就说明开始循环了

``` txt
# write my code here
class Solution:
    def hasCycle(self, head):
        nodeAddresses = {}
        pointer = head
        index = 0
        while pointer.next != None:
            nodeAddresses[index] = pointer
            if pointer.next in nodeAddresses.values():
                return True
            index += 1
            pointer = pointer.next
        return False
```

## Test Cases

``` text
Input: []
Output: false
```

服了，又是一个空链表的edge case, 下次得注意点

## Summary

> After read the answer, fill this part.

- Time Consumed: 8:50 - 9:09
- Category of the Problem:
  - Data Structure:
  - Algorithm:
- Any code worth to record here?
  - Method Name, Variable Name:
  - Useful build in method(function):
  - Algorithm implement template:
- Did I miss any edge case? Put it here:
- Complexity:
  - Time: O()
  - Space: O()

``` python
# Write the solution here
class Solution:
    def hasCycle(self, head):
        slow, fast = head, head

        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                return true
        
        return False
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
