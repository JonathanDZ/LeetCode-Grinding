# LeetCode Grinding Sheet 26

## Basic Information

- Start time: 9:11
- Problem: Contains Duplicate
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

这个题比上个题更简单。。只需要一个set，然后判断元素有没有在这个set里就行了。。

艹，这个题有巨坑，如果不用hashset，而只用普通的list查找，会直接超时。。。

``` txt
# write my code here
class Solution:
    def containsDuplicate(self, nums):
        s = set()
        for i in nums:
            if i in set:
                return True
            else:
                s.add(i)
        return False
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 9:11 - 9:22
- Category of the Problem:
  - Data Structure: hashSet
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
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
