# LeetCode Grinding Sheet Template

## Basic Information

- Start time:2022.5.26 7:54
- Problem: Flood Fill
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

这个题感觉好难，我一开始完全反应出来任何思路。。

也许可以遍历很多次，然后找到所有初始元素的邻域。。。但是这种方法一看就很差，因为如果最差的情况下，算法的复杂度是(MxN)^2，这样的算法是很烂的，想想有没有遍历次数更少的方法？

每遇到一个新的点，先把它自己的颜色改变，然后去检查上下左右的点，是否为原本的颜色，如果是就让这个点执行这个过程，如果上下左右所有的点都是不是原本的颜色，就返回退出

``` txt
# write my code here
class Solution:
    @staticmethod
    def fillAndCheck(image, sr, sc, newColor, oldColor):
        # oldColor = image[sr][sc]
        image[sr][sc] = newColor

        if sr - 1 >= 0 and image[sr-1][sc] == oldColor:
            Solution.fillAndCheck(image, sr - 1, sc, newColor, oldColor)
        if sr + 1 < len(image) and image[sr+1][sc] == oldColor:
            Solution.fillAndCheck(image, sr + 1, sc, newColor, oldColor)
        if sc - 1 >= 0 and image[sc-1][sc] == oldColor:
            Solution.fillAndCheck(image, sc - 1, sc, newColor, oldColor)
        if sc + 1 < len(image[0]) and image[sc+1][sc] == oldColor:
            Solution.fillAndCheck(image, sc + 1, sc, newColor, oldColor)
        return
    
    def floodFill(self, image, sr, sc, newColor):
        oldColor = image[sr][sc]
        Solution.fillAndCheck(image, sr, sc, newColor, oldColor)
        return image
```

## Test Cases

``` text
Input: [[0,0,0][0,1,1]], 1, 1, 1
Output: [[0,0,0][0,1,1]]
```

没想到还有填充原来的那个颜色的edge case。。。无语

## Summary

> After read the answer, fill this part.

- Time Consumed: 7：54 - 8：45
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
    def floodFill(self, image, sr, sc, newColor):
        if image[sr][sc] == newColor
            return image
        fill(image, sr, sc, image[sr][sc], newColor)
    
    @staticmethod
    def fill(image, sr, sc, color, newColor):
        if sr < 0 or sc < 0 or sr >= len(image) or sc >= len(image[0]) or image[sr][sc] != color
            return
        
        image[sr][sc] = newColor
        Solution.fill(image, sr - 1, sc, color, newColor)
        Solution.fill(image, sr + 1, sc, color, newColor)
        Solution.fill(image, sr, sc - 1, color, newColor)
        Solution.fill(image, sr, sc + 1, color, newColor)
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
