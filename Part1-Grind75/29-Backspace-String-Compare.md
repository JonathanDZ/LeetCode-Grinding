# LeetCode Grinding Sheet 29

## Basic Information

- Start time: 16:00
- Problem: Backspace String Compare
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

这个题的意思是我可以增加，然后又删除元素，我想不到有啥更好的办法，就直接一个数组遇到#就pop，其他的就append，然后比较就可以了

``` txt
# write my code here
class Solution:
    def backspaceCompare(self, s, t):
        sList = []
        tList = []

        for c in s:
            if c == '#':
                sList.pop()
            else:
                sList.append(c)
        
        for c in t:
            if c == '#':
                tList.pop()
            else:
                tList.append(c)
        
        if sList == tList:
            return True
        return False
        
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 21:34
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
# 倒过来看，如果遇到#就跳过后面的字符，然后以这种方式比较每一个字符，如果一致就输出true.
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
