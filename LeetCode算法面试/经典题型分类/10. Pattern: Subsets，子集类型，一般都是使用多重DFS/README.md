超级多的编程面试问题都会涉及到排列和组合问题。子集问题模式讲的是用BFS来处理这些问题。

这个模式是这样的：

给一组数字 [1, 5, 3]

我们从空集开始：[[]]
把第一个数（1），加到之前已经存在的集合中：[[], [1]];
把第二个数（5），加到之前的集合中得到：[[], [1], [5], [1,5]];
再加第三个数（3），则有：[[], [1], [5], [1,5], [3], [1,3], [5,3], [1,5,3]].
该模式的详细步骤如下：


<a href="https://ibb.co/7WgcrXX"><img src="https://i.ibb.co/Fwsv8KK/10.jpg" alt="10" border="0"></a>

如果判断这种子集模式：

* 问题需要咱们去找数字的组合或是排列


**经典题目：**

Subsets (easy)

Subsets With Duplicates (easy)

Permutations (medium)

String Permutations by changing case (medium)

Balanced Parentheses (hard)

Unique Generalized Abbreviations (hard)
