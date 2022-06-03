# LeetCode Grinding Sheet 23

## Basic Information

- Start time: 10:52
- Problem: Diameter of Binary Tree
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

感觉只需要计算根节点左右两边的最大深度就行了，写一个函数，找到左边和右边的最大深度，然后加在一起就结束了。

``` txt
# write my code here
class Solution:
    def findMaxDepth(self, node, maxPath):
        if not node:
            return 0
        # if not node.left and not node.right:
        #     return 1
        
        maxDepthL = self.findMaxDepth(node.left)
        maxDepthR = self.findMaxDepth(node.right)
        maxPath = max(maxPath, maxDepthL + maxDepthR)
        maxDepth = 1 + max(maxDepthL, maxDepthR)
        return maxDepth
    
    def diameterOfBinaryTree(self, root):
        maxDepth, maxPath = self.findMaxDepth(root, 0)
        return maxPath
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 10:52 - 11:39
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
    def diameterOfBinaryTree(self, root):
        res = [0]

        def dfs(root):
            if not root:
                return -1
            left = dfs(root,left)
            right = dfs(root.right)
            res[0] = max(res[0], 2 + left + right)

            return 1 + max(left, right)
        
        dfs(root)
        return res[0]
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
