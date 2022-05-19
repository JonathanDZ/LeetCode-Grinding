# LeetCode Grinding Sheet 2

## Basic Information

- Start time: 2022-5-19 16:05
- Problem: Valid Parentheses
  - Problem Description:
- Current list: Grind 75

## Constraints

只有三种括号，不用考虑其他的。并且输入只有括号，没有其他字符。

## Thinking Process

> Write down my thinking process like I'm trying to explain my ideas in the interview. If I stuck here for 15 minutes, jump to the next part.
> Be aware that:
>
> - Use readable method names, variable names;
> - Handle edge cases;
> - Don't use submit button as debugger, manual debug my code after finish it;
> - Write with good style;
> - Analyze Complexity after everything done;

我第一个想法就是设置一个list，可以记录所有括号的闭合状态，每添加一个左括号就在这个list中增加一个标记（三种括号用三种标记表示，比如1，2，3），如果它有对应的右括号就删掉这个标记，如果要删掉的标记与储存的标记不符，就返回错误，遍历完输入的字符串以后就检查这个list,如果这个list是空的就返回true，如果不为空就返回false。

``` python
class solution:
    def isValid(self, s):
        parenthesesAppendTypeMap = {
            '(': 1,
            '[': 2,
            '{': 3 
        }
        parenthesesRemoveTypeMap = {
            ')': 1,
            ']': 2,
            '}': 3 
        }
        statusList = []

        for char in s:
            if char in parenthesesAppendTypeMap:
                statusList.append(parenthesesAppendTypeMap[char])
            if char in parenthesesRemoveTypeMap:
                if (len(statusList) == 0):
                    return False
                if (parenthesesRemoveTypeMap[char] != statusList.pop())
                    return false
        if (len(statusList) == 0):
            return true
        else:
            return false
# 依然有很多错误，留下来以便未来进行纠错练习      
```

## Test Cases

``` text
Input: s = "{[()]}"
Output: true

Input: s = "([)]"
Output: false
```

我没想到的一点是，`.pop()`函数不能作用在空的list上，需要加入一个edge case.

## Summary

> After read the answer, fill this part.

- Time Consumed: 16：05 - 16：54
- Category of the Problem:
  - Data Structure:
    - stack: just use a simple list to implement that
    - hashmap (to match open and close parentheses)
  - Algorithm:
- Any code worth to record here?
  - Method Name, Variable Name:
  - Useful build in method(function):
  - Algorithm implement template:
    - To implement stack data structure with list in python:
      - use `.append()` and `.pop()` functions to add and remove items from the stack
- Did I miss any edge case? Put it here:
- Complexity:
  - Time: O(N)
  - Space: O(N)

```python
class Solution:
    def isValid(self, s: str) -> bool:
        stack = []
        closeToOpen = {
            ")": "(",
            "]": "[",
            "}": "{"
        }

        for c in s:
            if c in closeToOpen:
                if stack and stack[-1] == closeToOpen[c]:
                    stack.pop()
                else:
                    return False
            else:
                stack.append(c)
        
        return True if not stack else False
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
