# LeetCode Grinding Sheet 11

## Basic Information

- Start time: 8:40
- Problem: Lowest Common Ancestor of a Binary Search Tree
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

从我学习过的知识来看，我记得我只学过如何查找一个元素，也就是从root开始找题目给出的元素，但是我要在这个过程中记录我找到所有ancestors就可以比较这些ancestors, 然后找到LCA吧？

但是我发现我只需要找到他们搜索过程中最早有分歧的点就可以完成搜索了，我可以试试这个思路

``` txt
# write my code here
class Solution:
    @staticmethod
    def LCA(node, p, q):
        if p.val <= node.val and q.val >= node.val:
            return node
        if p.val >= node.val and q.val <= node.val:
            return node
        
        if p.val > node.val and q.val > node.val:
            LCANode = LCA(node.right, p, q)
        if p.val < node.val and q.val < node.val:
            LCANode = LCA(node.left, p, q)
        return LCANode

    def lowestCommonAncestor(self, root, p, q):
        return LCA(node, p, q)

```

## Test Cases

``` text
Input:
Output:
```

## Summary

> After read the answer, fill this part.

- Time Consumed: 8:40 - 9:25
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
    def lowestCommonAncestor(self, p, q):
        cur = root

        while cur:
            if p.val > cur.val and q.val > cur.val:
                cur = cur.right
            elif p.val < cur.val and q.val < cur.val:
                cur = cur.left
            else:
                return cur
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
