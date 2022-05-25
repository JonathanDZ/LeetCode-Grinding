# LeetCode Grinding Sheet 8

## Basic Information

- Start time: 14:44
- Problem: Binary Search
  - Problem Description:
- Current list: Grind 75

## Constraints

Array is sorted, and all the integer are unique.

## Thinking Process

> Write down my thinking process like I'm trying to explain my ideas in the interview. If I stuck here for 15 minutes, jump to the next part.
> Be aware that:
>
> - Use readable method names, variable names;
> - Handle edge cases;
> - Don't use submit button as debugger, manual debug my code after finish it;
> - Write with good style;
> - Analyze Complexity after everything done;

这个就是上课的时候教的二分搜索，按上课教的来做就行了，用两个指针递归实现就行

``` txt
# write my code here
class Solution:
    @staticmethod
    def binarySearch(nums, target, leftP, rightP):
        if nums[leftP] == target:
            return leftP
        if nums[rightP] == target:
            return rightP
        
        midP = (leftP + rightP) / 2
        if midP == leftP or midP == rightP:
            return -1 
        if nums[midP] > target:
            index = self.search(nums, target, leftP, midP)
        else:
            index = self.search(nums, target, midP, rightP)
        return index

    def search(self, nums, target):
        leftP, rightP = 0, len(nums) - 1
        return binarySearch(nums, target, leftP, rightP)
        

```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 14:44 - 15:30
- Category of the Problem:
  - Data Structure:
  - Algorithm:
- Any code worth to record here?
  - Method Name, Variable Name:
  - Useful build in method(function):
    - Use `//` operator to do floor division
  - Algorithm implement template:
- Did I miss any edge case? Put it here:
- Complexity:
  - Time: O()
  - Space: O()

``` python
# Write the solution here
class Solution:
    def search(self, nums, target):
        l, r = 0, len(nums) - 1

        while l <= r:
            m = (l + r) // 2
            if nums[m] > target:
                r = m - 1
            elif nums[m] < target:
                l = m + 1
            else:
                return m
        return -1
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
