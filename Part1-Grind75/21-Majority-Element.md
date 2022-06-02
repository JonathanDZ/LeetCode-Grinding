# LeetCode Grinding Sheet 21

## Basic Information

- Start time: 16:04
- Problem: Majority Element
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

不加限制的做出这道题应该很简单，就跟之前一样做一个简单的hashmap就可以了，但是这个似乎达不到O(1)的空间复杂度

``` txt
# write my code here
class Solution:
    def majorityElement(self, nums):
        elementToCounts = {}

        majorityCounts = len(nums) / 2.0
        for e in nums:
            if e in elementToCounts:
                elementToCounts[e] += 1
                if elementToCounts[e] > majorityCounts:
                    return e
            else:
                elementToCounts[e] = 1
        
        return None
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 16:04 - 16:22
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
    def majorityElement(self, nums):
        res, count = 0, 0

        for n in nums:
            if count == 0:
                res = n
            count += (1 if n == res else -1)
        return res
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
