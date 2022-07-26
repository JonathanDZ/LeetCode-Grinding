# LeetCode Grinding Sheet Template

## Basic Information

- Start time: 14:00
- Problem: Same Tree
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

这个太简单啦，上CS61B的时候就有讲过，应该随便写了

``` txt
# write my code here
class Solution(object):
    def isSameTree(self, p, q):
        if p is None and q is None:
            return True
        elif p.val != q.val:
            return false
        
        LIsSame = self.isSameTree(p.left, q.left)
        RIsSame = self.isSameTree(p.right, q.right)
        return LIsSame and RIsSame
        
        
  
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 14:15
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
# 跟我思路一模一样，不用写了
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
