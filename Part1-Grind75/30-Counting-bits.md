# LeetCode Grinding Sheet 30

## Basic Information

- Start time: 12:42
- Problem: Counting Bits
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

太久没做题了，感觉完全没有思路。。。

我觉得思路有点像递归，比如5=4+1，1比特数就等于1+1

就像初中教的那样一直除2可以得到一个数字的比特表示，但是我不应该对每个数字都这么搞，想想有没有什么递归的方法

比如，15 = 8 + 7， 然后 7 = 4 + 3, 然后 3 = 2 + 1, 所以总共就有4个1，想想这个用算法怎么表示，如何找到一个数字最近的2的整数幂

``` txt
# write my code here
class Solution(object):
    def findNearestPowerOf2(self, i):
        j = 1
        while j*2 <= i:
            j *= 2
        return j

    def countSingleBits(self, i, arr):
        if i is 0:
            return 0
        if i is 1:
            return 1

        j = self.findNearestPowerOf2(i)
        return 1 + arr[i - j]
    
    def countBits(self, n):
        arr = []
        for i in range(n+1 ):
            arr.append(self.countSingleBits(i, arr))
        return arr

```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 13:35
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
    def countBits(self, n: int) -> List[int]
        dp = [0] * (n + 1)
        offset = 1

        for i in range(1, n+1):
            if offset * 2 == i:
                offset = i
            dp[i] = 1 + dp[i - offset]
        
        return dp
```

## If I can't come up with an answer in 15 min

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
