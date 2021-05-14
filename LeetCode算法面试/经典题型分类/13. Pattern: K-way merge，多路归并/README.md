**K路归并能帮咱们解决那些涉及到多组排好序的数组的问题。每当你的输入是K个排好序的数组，你就可以用堆来高效顺序遍历其中所有数组的所有元素。你可以将每个数组中最小的一个元素加入到最小堆中，从而得到全
局最小值。当我们拿到这个全局最小值之后，再从该元素所在的数组里取出其后面紧挨着的元素，加入堆。如此往复直到处理完所有的元素**

<a href="https://ibb.co/x2WgGRL"><img src="https://i.ibb.co/3T2FWLd/13.jpg" alt="13" border="0"></a>

该模式是这样的运行的：

1. 把每个数组中的第一个元素都加入最小堆中

2. 取出堆顶元素（全局最小），将该元素放入排好序的结果集合里面

3. 将刚取出的元素所在的数组里面的下一个元素加入堆

4. 重复步骤2，3，直到处理完所有数字

**识别K路归并：**

* 该问题的输入是排好序的数组，链表或是矩阵
* 如果问题让咱们合并多个排好序的集合，或是需要找这些集合中最小的元素


**经典题目：**

Merge K Sorted Lists (medium)

Kth Smallest Number in M Sorted Lists (Medium)

Kth Smallest Number in a Sorted Matrix (Hard)

Smallest Number Range (Hard)
