# LeetCode Grinding Sheet 33

## Basic Information

- Start time: 8:49
- Problem: Longest Common Prefix
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

这有啥难的呢，一个一个比较一下不就完了

``` txt
# write my code here
class Solution:
    def longestCommonPrefix(self, strs):
        commonStr = ""
        minStrLen = sys.maxsize
        for i in range(0, len(strs)):
            minStrLen = min(minStrLen, len(strs[i]))

        for j in range(minStrLen):
            char = strs[0][j]
            for i in range(1, len(strs)):
                if char != strs[i][j]:
                    return commonStr
            commonStr += char
        return commonStr
```

## Test Cases

一不小心就越界了，想想怎么解决：

找到最小的str长度就行了

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 9:11
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
    def longestCommonPrefix(self, strs):
        res = ""

        for i in range(len(strs[0])):
            for s in strs:
                if i == len(s) or s[i] != strs[0][i]:
                    return res
            res += strs[0][i]
            
        return res
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
