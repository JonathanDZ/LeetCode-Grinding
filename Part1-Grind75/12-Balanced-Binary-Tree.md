# LeetCode Grinding Sheet 12

## Basic Information

- Start time: 10:32
- Problem: Balanced Binary Tree
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

这个题是要你判断这个二叉树是不是平衡的，我的直觉告诉我我可能需要遍历每一个子节点，然后看他们是不是在同一层

这种跟我之前做的那种搜索不同，这个是不是广度优先搜索？

我觉得我还是可以用之前的老路子去遍历所有的节点，但是这一次是记录叶子节点的深度最小值和最大值

上面这个想法是错误的，我感觉我整体思路就是有问题，必须要判断每一个子节点都是balanced才行，我完全走远了。。。不想改代码了，看答案了，这个题目收藏一下，以后重做。

``` txt
# write my code here
class Solution:
    @staticmethod
    def findDepth(node):
        if node.left == None and node.right == None:
            return 1, 1

        if node.left != None:
            maxDepthL, minDepthL = Solution.findDepth(node.left)
        else:
            maxDepthL, minDepthL = 0, sys.maxsize
        
        if node.right != None:
            maxDepthR, minDepthR = Solution.findDepth(node.right)
        else:
            maxDepthL, minDepthL = 0, sys.maxsize
        
        maxDepth = 1 + max(maxDepthL, maxDepthR)
        minDepth = 1 + min(minDepthR, minDepthR)

        return maxDepth, minDepth
    
    def isBalanced(self, root):
        maxDepth, minDepth = findDepth(node)
        if maxDepth - minDepth > 1
            return False
        else:
            return True
    

        
```

## Test Cases

``` text
Input:[1,null,2,null,3]
Output:false

Input:[1,2,2,3,null,null,3,4,null,null,4]
Output:false
```

这个问题比我想象中的复杂，要确定一个节点的左右两个子节点都是“balanced”而且depth还是一样的才行，我的思路从根本上就有问题

## Summary

> After read the answer, fill this part.

- Time Consumed:
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
    def isBalanced(self, root):

        def dfs(root):
            if not root: return [True, 0] # [balanced, depth]

            left, right = dfs(root.left), dfs(root.right)
            balanced = left[0] and right[0] and abs(left[1] - right[1]) <= 1

            return [balanced, 1 + max(left[1], right[1])]
        
        return dfs(root)[0]
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
