# LeetCode Grinding Sheet 19

## Basic Information

- Start time: 8:34
- Problem: Min Stack
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

Say some thing about the question:

``` txt
# write my code here
class MinStack:
    def __init__(self):
        stack = []
        min = None
    
    def push(self, val):
        stack.append(val)
        if min == None:
            min = val
        else:
            min = min(min, val)
    
    def pop(self):
        if stack:
            item = stack.pop()
            min = min(stack)
            return item
        else:
            return None
    
    def top(self):
        if stack:
            return stack[-1]
        else:
            return None
    
    def getMin(self):
        return min
```

## Test Cases

``` text
Input:
Output:
```

当数据全被取出的时候，stack为空，不能进行min()操作

## Summary

> After read the answer, fill this part.

- Time Consumed: 8:34 - 8:53
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
class MinStack:
    def __init__(self):
        self.stack = []
        self.minStack = []

    def push(self, val):
        self.stack.append(val)
        val = min(val, self.minStack[-1] if self.minStack else val)
        self.minStack.append(val)
    
    def pop(self):
        self.stack.pop()
        self.minStack.pop()
    
    def top(self):
        return self.stack[-1]
    
    def getMin(self):
        return self.minStack[-1]
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
