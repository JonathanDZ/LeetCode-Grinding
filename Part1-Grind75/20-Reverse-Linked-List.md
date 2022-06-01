# LeetCode Grinding Sheet 20

## Basic Information

- Start time: 9:12
- Problem: Reversed Linked List
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

终于做到这个大名鼎鼎的反转链表的题目了，天天听人说，自己还没做过

我就想装装逼，用递归来做，我感觉我对递归比较上瘾，哈哈

基本想法就是我如果要反转一个链表，就把第一个元素拆下来，放到已经反转后的后面所有链表后面就行了，应该很容易实现

但是我发现这个方法很没有效率

``` txt
# write my code here
class Solution:
    @staticmethod
    def reversedList(node):
        if node.next == None:
            return node
        
        head = Solution.reversedList(node.next)
        # nodeP = head
        # while nodeP.next != None:
        #     nodeP = nodeP.next
        # nodeP.next = node
        # node.next = None
        LastNode = node.next
        LastNode.next = node
        node.next = None
        return head
    
    def reverseList(self, head):
        return Solution.reversedList(head)
```

## Test Cases

``` text
Input:
Output:
```

注意空链表。。。又给我一个空链表。。

## Summary

> After read the answer, fill this part.

- Time Consumed: 9:12 - 9:40
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
# iterative solution:
class Solution:
    def reverseList(self, head):
        prev, curr = None, head

        while curr:
            nxt = curr.next
            curr.next = prev
            prev = curr
            curr = nxt
        return prev
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
