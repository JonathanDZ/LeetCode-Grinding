# LeetCode Grinding Sheet 36

## Basic Information

- Start time: 8:02
- Problem: Move Zeroes
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

简单

``` txt
# write my code here
class Solution:
    def moveZeroes(self, nums):
        count = 0
        while 0 in nums:
            nums.remove(0)
            count += 1
        while count > 0:
            nums.append(0)
            count -= 1
        
        return nums
```

## Test Cases

``` text
Input:
Output:
```

## Summary

这个题不难，但是它涉及一个很基本的算法，quick sort的partition

> After read the answer, fill this part.

- Time Consumed: 8:10
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
    def moveZeroes(self, nums):
        l = 0
        for r in range(len(nums)):
            if nums[r]:
                nums[l], nums[r] = nums[r], nums[l]
                l += 1
        return nums
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
