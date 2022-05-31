# LeetCode Grinding Sheet 18

## Basic Information

- Start time: 14:31
- Problem: Longest Palindrome
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

这个问题感觉有点怪异，感觉还是用hashmap统计每个字母的数量，如果大于等于2个，就加上这个数，然后在hashmap中删掉它，如果最后hashmap不为空，就最后再加一个，得到最长回文的长度

``` txt
# write my code here
class Solution:
    def longestPalindrome(self, s):
        charToCounts = {}
        
        for char in s:
            if char in charToCounts:
                charToCounts[char] += 1
            else:
                charToCounts[char] = 1
        
        sum = 0
        centerOccupied = False
        for char in charToCounts.keys():
            if charToCounts[char] % 2 == 0:
                sum += charToCounts[char]
                del charToCounts[char]
            elif charToCounts[char] > 1:
                if centerOccupied:
                    sum += charToCounts[char] - 1
                    del charToCounts[char]
                else:
                    centerOccupied = True
                    sum += charToCounts[char]
                    del charToCounts[char]

        
        if charToCounts and centerOccupied == False:
            return sum + 1
        else:
            return sum


```

## Test Cases

``` text
Input: bananas
Output: 5
```

一个很不好处理的情况就是这个回文中间可以有一个单独的数，但是这个数只能有一个，需要考虑所有奇数个的字母，只要它们存在，那么中间就会有一个单独的数，回文的长度就需要加一

## Summary

> After read the answer, fill this part.

- Time Consumed: 14:31 - 15:25
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
    def longestPalindrome(self, s):
        ans = 0
        for v in collections.Counter(s).itervalues():
            ans += v / 2 * 2
            if ans % 2 == 0 and v % 2 == 1:
                ans += 1
        
        return ans
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
