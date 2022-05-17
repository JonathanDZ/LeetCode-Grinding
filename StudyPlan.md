# Study Plan

刷题路线：

Blind 75 （Grind 75） List -> Top 100 liked List -> Patterns for Coding Questions List  -> All medium Problems (Sorted by AC, but don't do any problem with higher dislikes than likes)  -> CodeTop（国内大厂定向高频题，后期求职前精刷）

做题过程：

- 15分钟思考，想不出来就看答案
- 解题过程：
  - 使用C++或者Python编程（能用C++最好）
  - 练习白板编程（直接写在Markdown文档里，而不是IDE中），使用合适的函数名，变量名（这些都要从别人的代码里去学！）
  - 对着空气解释自己的思路（写出自己的thinking process，模拟对面试官解释的过程），写出自己的代码。然后思考有没有没有考虑到的边界问题（edge case）
  - 在Markdown文档中敲完代码之后，手动跑一个简单的样例（手动Debug），解决一些typo
    - 例如，我在Google Doc上跑样例的做法是，在屏幕上写出中间变量的当前取值，然后用鼠标光标告诉面试官现在程序跑到了哪一行代码，当前各个变量的取值是多少等等。主动测试的好处有很多。第一，这告诉面试官你很重视测试，而测试在实际生产中是非常非常重要的。第二，一个简单的样例常常可以找出不少类似于typo这样的小错误。第三，如果你的样例给得不错，那你甚至能够借助这个样例找到程序中的bug并纠正它，这总是要好过面试官发现并告诉你程序中存在着bug。主动测试时，你也可以确认你的程序可以很好地处理边界数据。
  - 把代码Copy到Leetcode当中提交，如果有问题就重复上面的步骤直到自认为bug free，再copy提交leetcode，尽量减少提交次数
  - 提交成功后分析算法复杂度
  - 题后总结
    - 记录自己的做题时间，
    - 尝试总结题目的解法并归类，（Data structure? Algorithm?）
    - 学习别人的函数、变量命名思路，对于好的代码可以记录下来，甚至整理成模板，
    - 对于自己没有想到的edge case可以做一个记录，方便自己查看
    - 记录算法复杂度
- 做不出来直接看答案的流程：
  - 分析自己为什么不会做这道题，是因为语言本身？还是因为算法不会？还是因为不知道这个数据结构？把这个信息记录下来，并花时间去学习相应的知识（优先算法书，编程语言的书，其次四大的课程视频，最后才是YouTube上的视频）
  - 记录一下自己学到的东西，尝试通俗易懂的解释一下（费曼学习法）
  - 抄一遍别人的code，体会编程的思路，以及函数、变量命名方式，记录下题目的类别（属于哪种解法，用什么数据结构）
  - 把知识点总结成Flashcard的形式，保存到我的repo当中

Pattern of Leetcode Problems:

> 出处：LeetCode按照怎样的顺序来刷题比较好？

- Sliding Window 滑动窗口类型
- Two Points 双指针类型
- Fast & Slow Pointers 快慢指针类型
- Merge Intervals 区间合并类型
- Cyclic Sort 循环排序
- In-place Reversal of a LinkedList 链表翻转
- Tree Breadth First Search 树上的BFS
- Tree Depth First Search 树上的DFS
- Two Heaps 双堆类型
- Pattern: Subsets 子集类型，一般都是使用多重DFS
- Modified Binary Search 改造过的二分
- Pattern: Top ‘K’ Elements 前K个系列
- K-way merge 多路归并
- 0/1 Knapsack (Dynamic Programming) 0/1背包类型
- Topological Sort (Graph) 拓扑排序类型

做题习惯（Style）：

- Coding interview university
- Algorithm Design Canvas
- Crack the coding interview
- Wu的校招面试经验
- CS61B Style Guide
- CS61A Style Guide

编程语言（C++ & Python）：

- Programming Language Resources
- CS 106L Standard C++ Programming
- A Guide for Transitioning from Python to C++
- CS106L C++ course reader
- 《算法笔记》胡凡著

算法：

- Data Structures and Algorithms in Python
- Data Structures and Algorithms in C++, 2nd Edition
- Algorithm 4th edition

面试指南：

- Cracking the coding interview
- 九章算法

其他资源：

- CS61B/九章算法/YouTube (NeetCode)/Leetcode Learn（不懂的概念可以看课程，或者看leetcode自己的教程，或者上YouTube去查）
- LeetCode按照怎样的顺序来刷题比较好？- 穷码农的回答
- Grokking the Coding Interview: Patterns for Coding Questions
- CodeTop 国内大厂高频题
