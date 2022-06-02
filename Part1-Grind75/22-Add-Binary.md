# LeetCode Grinding Sheet 22

## Basic Information

- Start time: 16:44
- Problem: Add Binary
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

不停的pop数组的最后一位，设置好进位的标签，最后当所有数组都pop空掉之后，看有没有进位，有就再加一，没有就直接输出

``` txt
# write my code here
class Solution:
    def addBinary(self, a, b):
        advance = 0
        output = []
        a = list(a)
        b = list(b)

        while a or b:
            itemA = (int(a.pop()) if a else 0)
            itemB = (int(b.pop()) if b else 0)
            sum = itemA + itemB + advance
            if sum == 3:
                output.insert(0, 1)
                advance = 1
            if sum == 2:
                output.insert(0, 0)
                advance = 1
            if sum == 1:
                output.insert(0, 1)
                advance = 0
            if sum == 0:
                output.insert(0, 0)
                advance = 0
        
        if advance == 1:
            output.insert(0, 1)
        return ''.join(str(e) for e in output)
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 16:44 - 17:13
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
    def addBinary(self, a, b):
        res = ""
        carry = 0

        a, b = a[::-1], b[::-1]

        for i in range(max(len(a), len(b))):
            digitA = ord(a[i]) - ord("0") if i < len(a) else 0
            digitB = ord(b[i]) - ord("0") if i < len(a) else 0

            total = digitA + digitB + carry 
            char = str(total % 2)
            res = char + res
            carry = total // 2
        
        if carry:
            res = "1" + res
        return res
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
