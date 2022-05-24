# LeetCode Grinding Sheet 6

## Basic Information

- Start time: 15:07
- Problem: Invert Binary Tree
  - Problem Description:
- Current list: Grind 75

## Constraints

给一个二叉树，反转它的顺序

## Thinking Process

> Write down my thinking process like I'm trying to explain my ideas in the interview. If I stuck here for 15 minutes, jump to the next part.
> Be aware that:
>
> - Use readable method names, variable names;
> - Handle edge cases;
> - Don't use submit button as debugger, manual debug my code after finish it;
> - Write with good style;
> - Analyze Complexity after everything done;

我觉得我只有一个很直观的想法就是递归的翻转所有包含子节点的节点，只需要交换所有含有子节点的父节点就可以了

``` txt
# write my code here
class Solution(object):
    def switchChildren(self, node):
        if node.left == None and node.right == None:
            return node
        
        if node.left is not None:
            node.left = switchChildren(node.left)
        if node.right is not None:
            node.right = switchChildren(node.right)
        
        temp = node.right
        node.right = node.left
        node.left = temp
        return node
    
    def invertTree(self, root):
        return switchChildren(root)
# 感觉python对static method的支持很不友好，也许是不提倡这样做？
# 以后复盘的时候可以尝试把这里static method的调用改正确
```

## Test Cases

``` text
Input: []
Output: []
```

我没考虑到完全空的二叉树的情况。。。。

## Summary

> After read the answer, fill this part.

- Time Consumed: 15:07 - 16:00 (这次还包括看答案的时间)
- Category of the Problem:
  - Data Structure: Binary Tree
  - Algorithm: Recursion
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
    def invertTree(self, root: TreeNode) -> TreeNode:
        if not root:
            return None
        
        # swap the children
        tmp = root.left
        root.left = root.right
        root.right = tmp

        self.invertTree(root.left)
        self.invertTree(root.right)
        return root
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
