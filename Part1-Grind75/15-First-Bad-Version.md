# LeetCode Grinding Sheet 15

## Basic Information

- Start time: 9:02
- Problem: First Bad Version
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

这个题看起来好简单。。就用二分法找到起始位置就行，但是这个二分法得稍微修改一下

先检查中间节点，如果是true，就检查中间节点之前的节点，如果是false就输出这个中间节点，如果是之前那个节点是true，就把它设为终止节点；如果中间节点是false，就检查中间节点之后的节点，如果那个节点是true, 就输出之后的那个节点，如果那个节点是false, 就把它设为起始节点

``` txt
# write my code here
class Solution:
    @staticmethod
    def findBadVersion(leftP, rightP):
        if leftP == rightP:
            return leftP
        if leftP == rightP - 1:
            if isBadVersion(leftP):
                return leftP
            else:
                return rightP
        
        midP = (leftP + rightP) // 2
        if isBadVersion(midP):
            if isBadVersion(midP-1):
                return Solution.findBadVersion(leftP, midP-1)
            else:
                return midP
        else:
            if isBadVersion(midP+1):
                return midP + 1
            else:
                return Solution.findBadVersion(midP+1, rightP)

    def firstBadVersion(self, n):
        return Solution.findBadVersion(1, n)

```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 9:02 - 9:43
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
    def firstBadVersion(self, n):
        left = 0
        right = n

        while left < right:
            midpoint = left + (right - left) // 2
            if isBadVersion(midpoint):
                right = midpoint
            else:
                left = midpoint + 1

        if left == right and isBadVersion(left):
            return left
        
        return -1
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
