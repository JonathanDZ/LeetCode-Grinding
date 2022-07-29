# LeetCode Grinding Sheet 37

## Basic Information

- Start time: 9:36
- Problem: Symmetric Tree
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

又一个有意思的遍历题目,感觉这个并不能递归，因为左边是对称和右边是对称的并不代表整个树都是对称的，应该同时从左往右遍历，又从右往左遍历，看是否相等

``` txt
# write my code here
class Solution:
    def isSymmetricRecursive(self, nodeL, nodeR):
        if not nodeL and not nodeR:
            return True
        if nodeL or nodeR:
            return False
        if nodeL.val != nodeR.val:
            return False
        
        compareLLRR = self.isSymmetricRecursive(nodeL.left, nodeR.right)
        compareLRRL = self.isSymmetricRecursive(nodeL.right, nodeR.left)
        return compareLLRR and compareLRRL

    def isSymmetric(self, root):
        return self.isSymmetricRecursive(root, root)
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 10:06
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
# 解法一模一样，不用写了，有一个广度遍历的方法，后续再练习吧
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
