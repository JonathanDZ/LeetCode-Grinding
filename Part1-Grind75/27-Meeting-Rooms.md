# LeetCode Grinding Sheet 27

## Basic Information

- Start time: 14:47
- Problem: Meeting Rooms
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

感觉这个像stack或者queue能够解决的问题，我想到一个方法，我先把所有的元素放进hashmap（s -> e），然后把所有起始时间进行排序，然后根据这个排序访问所有的终止位置，然后比较下一个起始位置，如果下一个起始位置小于上一个终止位置，就返回false

``` txt
# write my code here
class Solution:
    def can_attend_meetings(self, intervals):
        startToEnd = {}
        for interval in intervals:
            startToEnd[interval.start] = interval.end

        lastStart = 0
        lastEnd = 0
        for start in sorted(startToEnd.keys()):
            end = startToEnd[start]
            if lastEnd > start:
                return false
            lastStart = start
            lastEnd = end
        
        return True
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 15:09 没有对答案，因为是premium题目
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
    def can_attend_meetings(self, intervals):
        intervals.sort(key = lambda i : i.start)

        for i in range(1, len(intervals)):
            i1 = intervals[i - 1]
            i2 = intervals[i]

            if i1.end > i2.start:
                return False
        
        return True
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
