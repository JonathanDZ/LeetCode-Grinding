# LeetCode Grinding Sheet 1

## Basic Information

- Start time: 2021.5.18 19:19
- Problem: Two Sum
  - Problem Description: Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target. You may assume that each input would have exactly one solution, and you may not use the same element twice. You can return the answer in any order.
- Current list: Grind 75

## Constraints

只有一个结果，所以只要找到一个就够了

## Thinking Process

> Write down my thinking process like I'm trying to explain my ideas in the interview. If I stuck here for 15 minutes, jump to the next part.
> Be aware that:
>
> - Use readable method names, variable names;
> - Handle edge cases;
> - Don't use submit button as debugger, manual debug my code after finish it;
> - Write with good style;
> - Analyze Complexity after everything done;

先给数组排序，然后在数组里一头一尾设置两个指针a和b，指针上的两个元素相加大于target,就把后一个指针前移一位，如果相加小于target，就把后一个指针后移一位，如果相加结果一致，就输出指针指向的两个值，数据结构使用array就行了

但是这样有两个问题：

 1. 如何排序？我印象中java中有内置排序法，好像在collections当中，Python和C++的内置排序方法是什么？
 2. 会不会没有valid answer? 没有的话，怎么处理？我自己跑了一下我的测试样例，发现如果没有结果的话，两个指针会交叉，所以只需要设置如果两个指针都指向同一个数字的时候还不满足target，就输出“Invalid Input”，然后直接退出（我有个问题：输出什么错误提示比较规范？）

根据第二个问题，我还需要设置一个while循环，条件设为`a <= b`就可以了

- 我该如何定义返回类型？好像不用定义......
- Python怎么写注解来着？
- Python的array长度怎么得到来着？
- How to return null in Python?
- 如何在Python中对数组进行排序？好像直接`.sort()`就行了

> 20:18 被迫暂停写程序，等会儿继续
> 21：05 继续写代码

```python
Class Solution(object):
  def sort(self):
    # sort the array
    return 

  def twoSum(self, nums, target):
    numsCopy = list(nums)
    numsSorted = nums.sort()

    pointerFront = 0
    pointerEnd = num.len()
    while (pointerFront <= pointerEnd):
      currentSum = numsSorted[pointerFront] + numsSorted[pointerEnd]
      if (currentSum == target):
        indexFront = numsCopy.index(pointerFront)
        indexEnd = numsCopy.index(pointerEnd)
        if (indexFront == indexEnd):
          indexEnd = numsCopy.index(pointerEnd, indexFront)
        return [indexFront, indexEnd]
      if (currentSum > target):
        pointerEnd -= 1
      if (currentSum < target):
        pointerFront += 1
    print("Invalid Input")
    return null;

  # 这个程序里有好几个错误，我也不修改了，保留下来以后用于复盘
```

## Test Cases

Input: [2,4,6,8,10,12], target = 17

Output: Invalid Input

Input: [2,2], target = 4

Output: [0,1]

我没考虑到把排序之后的坐标变换回去！

我怎么才能把原始的坐标记录下来呢？

我可以把所有的index都用dictionary记录下来，但是要是有很多个elements都是一个数字该怎么办？

- 当搜索的前一个index和后一个index一样的时候，重新搜索一次后一个pointer所指向的index

一个重大错误：我发现我直接copy一个字符串给另一个字符串的时候（`numsCopy = nums`）只是copy了它的地址！并没有分配新的内存给它！如果其中一个数组变了，另一个也会跟着变！！！

正确做法：`listCopy = list(list)`

## Summary

> After read the answer, fill this part.

- Time Consumed: 19:19 - 22:30 - 40min(去做核酸)
- Category of the Problem:
  - Data Structure: HashMap
  - Algorithm: Just loop through a HashMap
- Any code worth to record here?
  - Method Name, Variable Name:
  - Useful build in method:
    - `for i, n in enumerate(iterable, start=0)` 这个可以枚举数组的每一个元素（放在n当中），然后同时给出每个元素的index（i）
    - HashMap
      - 初始化：`hashMap = {}`
      - 添加元素：`hashMap[index] = item`
      - 查找元素：`item = hashMap[index]`
  - Algorithm implement template:
- Did I miss any edge case? Put it here:
- Complexity: O(N)

``` python
class Solution(object):
    def twoSum(self, nums, target):
        prevMap = {} # val: index

        for i, n in enumerate(nums): # i: count, n: item
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i
        return
```

## If I can't come up with an answer in 15 min...

> > Only do this if I go direct to read the answer.
>
> - Why can't I do this?
>   - Program language? Data structure? Algorithm?
> - Write down what I just learned from the answer: (In the form of flashcard)
> - Manually copy the sample answer one time
