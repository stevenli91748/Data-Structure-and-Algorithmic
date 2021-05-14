**树形DFS基于深搜（Depth First Search (DFS)）技术来实现树的遍历。咱们可以用递归（或是显示栈，如果你想用迭代方式的话）来记录遍历过程中访问过的父节点。该模式的运行方式是从根节点开始，如果该节点
不是叶子节点，我们需要干三件事：**

**需要区别我们是先处理根节点（pre-order，前序），
处理孩子节点之间处理根节点（in-order，中序），
还是处理完所有孩子再处理根节点（post-order，后序）。
递归处理当前节点的左右孩子。**


识别树形DFS：

你需要按前中后序的DFS方式遍历树
如果该问题的解一般离叶子节点比较近。
经典题目：

Binary Tree Path Sum (easy)

All Paths for a Sum (medium)

Sum of Path Numbers (medium)

Path With Given Sequence (medium)

Count Paths for a Sum (medium)
