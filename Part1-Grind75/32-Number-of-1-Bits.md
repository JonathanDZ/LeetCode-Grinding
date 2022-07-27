# LeetCode Grinding Sheet 32

## Basic Information

- Start time: 8:09
- Problem: Number of 1 Bits
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

感觉和上一道题（30）基本差不多啊，应该是差不多的解法

就除2直到0？或者像上次那样，计算它最近的2的整数幂？上次已经写过第二种方法了，这次来写写最传统的方法

``` txt
# write my code here
class Solution(object):
    def hammingWeight(self, n):
        count = 0
        while n > 0:
            if n % 2 is 1:
                count += 1
            n /= 2
        
        return count
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 8:24
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
    def hammingWeight(self, n):
        res = 0
        while n:
            n &= (n - 1)
            res += 1
        return res
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
