# LeetCode Grinding Sheet 14

## Basic Information

- Start time: 9:28
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

看着这个题我有点懵逼，这是啥，怎么跟之前的题格式不一样了。。。

我现在算是理解这个题意了（用两个杯子，模拟一个队列），但是就是不知道该咋写。。。

``` txt
# write my code here
class MyQueue:
    def __init__(self):
        self.stack1 = []
        self.stack2 = []
    
    def push(self, x):
        self.stack1.append(x)
    
    def pop(self):
        if self.stack2:
            return self.stack2.pop()
        else:
            if self.stack1:
                while self.stack1 != None:
                    item = self.stack1.pop()
                    self.stack2.append(item)
                return self.pop()
            else:
                return None
    
    def peek(self)
        if self.stack2:
            return self.stack2[-1]
        else:
            if self.stack1:
                while self.stack1 != None:
                    item = self.stack1.pop()
                    self.stack2.append(item)
                return self.peek()
            else:
                return None
    
    def empty(self):
        if not self.stack1 and not self.stack2:
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

- Time Consumed: 9:28 - 10:33
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
# 暂时没有在网上找到合适的python题解，我自己实现的通过了我感觉就行了，以后可以再琢磨
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time

这种题目形式我还没见过，而且我对stack和queue也不熟，完全没搞懂咋整的。
