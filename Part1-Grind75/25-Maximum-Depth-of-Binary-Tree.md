# LeetCode Grinding Sheet 25

## Basic Information

- Start time: 8:23
- Problem: Maximum Depth of Binary Tree
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

这个我很早就写过了。。太简单了

``` txt
# write my code here
class Solution:
    def maxDepth(self, root):
        if not root:
            return 0
        
        maxDepthL = self.maxDepth(root.left)
        maxDepthR = self.maxDepth(root.right)
        maxDepth = 1 + max(maxDepthL, maxDepthR)
        return maxDepth
```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 8:23 - 8:30
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
# BFS solution
class Solution:
    def maxDepth(self, root):
        if not root:
            return 0
        
        level = 0
        q = deque([root])
        while q:
            for i in range(len(q)):
                node = q.popleft()
                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)
                level += 1
        return level

# Iterative DFS
class Solution:
    def maxDepth(self, root):
        stack = [[root, 1]]
        res = 0

        while stack:
            node, depth = stack.pop()

            if node:
                res = max(res, depth)
                stack.append([node.left, depth + 1])
                stack.append([node.right, depth + 1])
        return res
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
