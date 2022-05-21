# LeetCode Grinding Sheet 4

## Basic Information

- Start time: 2022.5.21 9:42
- Problem: Best Time to Buy and Sell Stock
  - Problem Description:
- Current list: Grind 75

## Constraints

给出一段时间的股价，选择最好的买入卖出时机，输出profit。
如果无法获得收益，返回0。

## Thinking Process

> Write down my thinking process like I'm trying to explain my ideas in the interview. If I stuck here for 15 minutes, jump to the next part.
> Be aware that:
>
> - Use readable method names, variable names;
> - Handle edge cases;
> - Don't use submit button as debugger, manual debug my code after finish it;
> - Write with good style;
> - Analyze Complexity after everything done;

在这个问题里我就是要找到一个全局最小值，以及这个全局最小值之后的全局最大值，最简单的做法就是遍历一遍找到最小值，然后再遍历一遍最小值之后的数组元素，找到其中的最大值，相减得到profit，如果小于0就输出0。时间复杂度为O(N), 空间复杂度为O(1)

可以尝试同时找最小值和最大值，当最小值的index大于最大值的index的时候，不管新用于比较的元素大小如何，都直接用最小值右边的元素值替代最大值

``` txt
# write my code here
class Solution:
    def maxProfit(self, prices):
        peak = 0
        bottom = 0

        for i in len(prices):
            if prices[bottom] > prices[i]:
                bottom = i
                peak = -1
            if i == bottom + 1:
                peak = i
                continue
            if prices[peak] < prices[i]:
                peak = i
        
        if peak < 0:
            return 0
        profit = prices[peak] - prices[bottom]
        return profit if profit else return 0 
```

找到每一个波峰波谷，然后计算所有的profit，找到最大值输出

```
class Solution:
    def maxProfit(self, prices):
        peak = 0
        bottom = 0
        profits = []
        lastPrice = prices[0]

        for i in range(len(profit)):
            if prices[i] > lastPrice:
                peak = i
                lastPrice = prices[i]
            if prices[i] <= lastPrice:
                if peak == bottom:
                    peak = i
                    bottom = i
                else:
                    profit = prices[peak] - prices[bottom]
                    profits.append(profit)
                    peak = i
                    bottom = i
                lastPrice = prices[i]
        
        profit = prices[peak] - prices[bottom]
        profits.append(profit)
        return max(profits)
```

找到i为止的局部最优值，peak和bottom，以及newPeak和newBottom，如果新的局部最大最小值的差比之前那个大，就用新的bottom和peak代替原来的bottom和peak。

``` txt
# write my code here
class Solution:
    def maxProfit(self, prices):
        peak = -1
        newPeak = -1
        bottom = 0
        newBottom = 0

        for i in len(prices):
            if prices[i] < prices[newBottom]:
                newBottom = i
            if i == bottom + 1:
                peak = i
            if i == newBottom + 1:
                newPeak = i
            if peak >= 0 && prices[peak] < prices[i]:
                peak = i
            if newPeak >= 0 && prices[newPeak] <= prices[i]:
                newPeak = i
                profit = prices[peak] - prices[bottom]
                newProfit = prices[newPeak] - prices[newBottom]
                if newProfit > profit:
                    bottom = newBottom
                    peak = newPeak
                    newPeak = -1

        
        if peak < 0:
            return 0
        profit = prices[peak] - prices[bottom]
        return profit if profit else return 0 
```

## Test Cases

``` text
Input: [7,6,4,3,2,1]
Output:[0]

Input: [2,4,1]
Output:[0]

Input: [3,10,2,8,1,6,0]
Output:[7]
```

这个题我完全想错了，应该是要记录每一个波谷到波峰的值，然后进行比较，找到最大的那个波谷到波峰的差

上面这个想法也不对，我不知道该怎么办了

我的思路一开始就走偏了，不应该去找股价的最大值和最小值，而是找到最小值和从这个点出发能产生的最大利润

## Summary

> After read the answer, fill this part.

- Time Consumed: 9:42 - 12:21
- Category of the Problem:
  - Data Structure: array
  - Algorithm: Sliding Window
- Any code worth to record here?
  - Method Name, Variable Name:
  - Useful build in method(function):
  - Algorithm implement template:
- Did I miss any edge case? Put it here:
- Complexity:
  - Time: O(N)
  - Space: O(1)

``` python
# Write the solution here
class Solution:
    def maxProfit(self, prices):
        l, r = 0, 1 # left = buy, right = sell
        maxP = 0

        while r < len(prices):
            if prices[l] < prices[r]:
                profit = prices[r] - prices[l]
                maxP = max(maxP, profit)
            else:
                l = r
            r += 1
        
        return maxP
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
