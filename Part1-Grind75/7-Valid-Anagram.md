# LeetCode Grinding Sheet 7

## Basic Information

- Start time: 14:18
- Problem: Valid Anagram
  - Problem Description:
- Current list: Grind 75

## Constraints

给出两个字符串，判断字符串是不是另一个的重新排列组合

## Thinking Process

> Write down my thinking process like I'm trying to explain my ideas in the interview. If I stuck here for 15 minutes, jump to the next part.
> Be aware that:
>
> - Use readable method names, variable names;
> - Handle edge cases;
> - Don't use submit button as debugger, manual debug my code after finish it;
> - Write with good style;
> - Analyze Complexity after everything done;

我觉得这个题超级简单啊，直接把第一个字符串转化成一个hashmap，然后遍历第二个字符串的时候检查hashmap里有没有这些元素就行了，非常简单。

``` txt
# write my code here
class Solution:
    def isAnagram(self, s, t):
        hashmap = {} # char -> number
        
        for c in s:
            if c in hashmap:
                hashmap[c] += 1
            else:
                hashmap[c] = 1
        
        for c in t:
            if c in hashmap:
                if hashmap[c] == 1:
                    del hashmap[c]
                else:
                    hashmap[c] -= 1
            else:
                return False
        if not hashmap:
            return True
        else:
            return False

```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.
>
> 没啥好总结的，这个题很简单

- Time Consumed: 14:18 - 14:33
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
    def is Anagram(self, s, t):
        return sorted(s) == sorted(t)
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
