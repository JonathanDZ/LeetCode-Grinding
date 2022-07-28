# LeetCode Grinding Sheet 34

## Basic Information

- Start time: 7:56
- Problem: Single Number
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

我看到这个题目第一个想法居然是快慢指针，但应该不是这个

最简单的想法，直接排序，然后一个一个看就行了，但这样太low了，我想想有没有更聪明的办法

看了看题目问题，排序是不行的，时间复杂度必须是O(n),空间复杂度O(1)

我想不出空间复杂度是O(1)的方法。。我就写写最简单的那个吧

``` txt
# write my code here
class Solution:
    def singleNumber(self, nums):
        existNums = []
        for num in nums:
            if num in existNums:
                existNums.remove(num)
            else:
                existNums.append(num)
        
        return existNums[0]
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

最近这几个题要使用到位操作，这个是我非常不熟悉的东西，我一定要好好练习一下（或者以后有时间要专题练习一下）

- Time Consumed: 8:15
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
    def singleNumber(self, nums):
        res = 0
        for n in nums:
            res = n ^ res
        return res
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
