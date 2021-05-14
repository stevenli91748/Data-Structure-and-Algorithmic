当你需要解决的问题的输入是排好序的数组，链表，或是排好序的矩阵，要求咱们寻找某些特定元素。这个时候的不二选择就是二分搜索。这种模式是一种超级牛的用二分来解决问题的方式。

对于一组满足上升排列的数集来说，这种模式的步骤是这样的：

首先，算出左右端点的中点。最简单的方式是这样的：middle = (start + end) / 2。但这种计算方式有不小的概率会出现整数越界。因此一般都推荐另外这种写法：middle = start + (end — start) / 2
如果要找的目标改好和中点所在的数值相等，我们返回中点的下标就行
如果目标不等的话：我们就有两种移动方式了
如果目标比中点在的值小（key < arr[middle]）：将下一步搜索空间放到左边（end = middle - 1）
如果比中点的值大，则继续在右边搜索，丢弃左边：left = middle + 1
图示该过程的话，如下图所示

<a href="https://ibb.co/z4Ywbtv"><img src="https://i.ibb.co/DRynkj2/11.jpg" alt="11" border="0"></a>

**经典题目：**

Order-agnostic Binary Search (easy)

Ceiling of a Number (medium)

Next Letter (medium)

Number Range (medium)

Search in a Sorted Infinite Array (medium)

Minimum Difference Element (medium)

Bitonic Array Maximum (easy)
