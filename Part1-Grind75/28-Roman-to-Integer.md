# LeetCode Grinding Sheet 28

## Basic Information

- Start time: 16:14
- Problem: Roman to Integer
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

我觉得这个题跟上一题meeting rooms很像，都是要检查下一个元素是否违反了正常的次序，然后再输出结果

这样的话就直接遍历整个字符串，当看到下一个元素没有违反规则的时候，加上它，违法规则就减去上一个元素

``` txt
# write my code here
class Solution:
    def romanToInt(self, s):
        length = len(s)
        romanToInteger = {
            'I': 1,
            'V': 5,
            'X': 10,
            'L': 50,
            'C': 100,
            'D': 500,
            'M': 1000
            }
        if length == 1:
            return romanToInteger[s[0]]
        
        value = 0
        for i in range(1, length):
            if romanToInteger[s[i]] > romanToInteger[s[i - 1]]:
                value -= romanToInteger[s[i - 1]]
            else:
                value += romanToInteger[s[i - 1]]
        value += romanToInteger[s[-1]]

        return value
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 16:53 今天肚子不舒服，完全集中不了注意力
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
# 思路完全一致，不用写了
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
