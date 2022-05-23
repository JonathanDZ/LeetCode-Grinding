# LeetCode Grinding Sheet 5

## Basic Information

- Start time: 9：54
- Problem: Valid Palindrome
  - Problem Description:
- Current list: Grind 75

## Constraints

去除所有除了数字和字母之外的字符，从前往后读和从后往前读一模一样，这种就是Palindrome

## Thinking Process

> Write down my thinking process like I'm trying to explain my ideas in the interview. If I stuck here for 15 minutes, jump to the next part.
> Be aware that:
>
> - Use readable method names, variable names;
> - Handle edge cases;
> - Don't use submit button as debugger, manual debug my code after finish it;
> - Write with good style;
> - Analyze Complexity after everything done;

先遍历一遍去除其他字符，然后再遍历一遍，设定两个指针，一个从前往后，一个从后往前，依次判断每个字符是否一致，当后一个指针大于等于前一个指针的时候停止，并输出true,如果有不同就return false。

其实不用去除，只需要遍历到非法字符的时候跳过就行了；另外还要把大写字符转成小写字符

但是这两种方法复杂度都是O(N), 完全没有必要搞得那么复杂，就用最简单的方式就好。

``` python
# write my code here
class Solution:
    def isPalindrome(self, s):
        validString = ""
        for c in s:
            if c.isalpha() or c.isdigit():
                validString += c
        
        if not validString:
            return True
        
        validString = validString.lower()
        forwardP = 0
        backwardP = len(validString) - 1
        while backwardP >= forwardP:
            if validString[forwardP] == validString[backwardP]:
                forwardP += 1
                backwardP -= 1
            else:
                return False
        return True

```

## Test Cases

``` text
Input:
Output:
```

如果只有零个或者一个字符

## Summary

> After read the answer, fill this part.

- Time Consumed: 9:54 - 10:34
- Category of the Problem:
  - Data Structure:
  - Algorithm:
- Any code worth to record here?
  - Method Name, Variable Name:
  - Useful build in method(function):
    - check if the character is alphanumerical: `.isalnum()`
    - python slice notation [check here](https://stackoverflow.com/questions/509211/understanding-slicing)
    , this is super useful when manipulating the array like data.
    - `ord(char)` return the ASCII number of the character
  - Algorithm implement template:
- Did I miss any edge case? Put it here:
- Complexity:
  - Time: O()
  - Space: O()

``` python
# Write the solution here
class Solution:
  def isPalindrome(self, s):
    newStr = ""

    for c in s:
      if c.isalnum():
        newStr += c.lower()
    return newStr == newStr[::-1]

class Solution:
  def alphaNum(self, c):
    return (ord('A') <= ord(c) <= ord('Z') or
            ord('a') <= ord(c) <= ord('z') or
            ord('0') <= ord(c) <= ord('9'))

  def isPalindrome(self, s):
    l, r = 0, len(s) - 1

    while l < r:
      while l < r and not self.alphaNum(s[l]):
        l += 1
      while l < r and not self.alphaNum(s[r]):
        r -= 1
      if s[l].lower() != s[r].lower():
        return False
      l, r = l + 1, r - 1
    return True

```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
