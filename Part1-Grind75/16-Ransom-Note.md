# LeetCode Grinding Sheet 16

## Basic Information

- Start time: 10:00
- Problem:
  - Problem Description:
- Current list:

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

这个题也很简单，就把magazine里的单词转化成一个hashSet，然后用ransomNote中的元素去查找就行了，如果这个hashSet里没有想要的元素就输出false

我完全理解错了。。。这个元素是用掉了就没有了，如果需要多个元素，magazine里也应该有等量的元素才行

``` txt
# write my code here
class Solution:
    def canConstruct(self, ransomNote, magazine):
        charSet = []
        for char in magazine:
            charSet.append(char)
        
        for char in ransomNote:
            if char not in charSet:
                return False
            charSet.remove(char)
        
        return True
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 10:00 - 10:15
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
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
