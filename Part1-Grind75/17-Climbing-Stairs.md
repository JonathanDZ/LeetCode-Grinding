# LeetCode Grinding Sheet 17

## Basic Information

- Start time: 13:10
- Problem: Climbing Stairs
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

这个问题直接想很难想，但是我马上就想到，是否可以用递归的思想来实现这个过程？

好吧，我似乎求出了这个问题的通式，直接用通式计算就好了
> 比如有6个的时候,公式为：$(^6_0) + (^5_1)+(^4_2)+(^3_3)$
>
> 有n个就会变成：$(^n_0)+(^{n-1}_1)+(^{n-2}_2)+(^{n-3}_3)+ \dots +(^{n/2}_{n/2})$
>
>奇数个的情况下：$(^n_0)+(^{n-1}_1)+(^{n-2}_2)+(^{n-3}_3)+ \dots +(^{n-1/2}_{n+1/2})$

``` txt
# write my code here
import math
class Solution:
    def comb(self, n, r):
        f = math.factorial
        return f(n) // f(r) // f(n - r)
    def climbStairs(self, n):
        # from m choose r
        m, r = n, 0
        sum = 0
        while m >= r:
            sum += self.comb(m, r)
            m -= 1
            r += 1
        return sum
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 13:10 - 13:53
- Category of the Problem:
  - Data Structure:
  - Algorithm: `Bottom Up Dynamic Programming`
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
    def climbStairs(self, n):
        one, two = 1, 1

        for i in range(n - 1):
            temp = one
            one = one + two
            two = temp
        
        return one
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
