**任何让我们求解最大/最小/最频繁的K个元素的题，都遵循这种模式。用来记录这种前K类型的最佳数据结构就是堆了（译者注：在Java中，改了个名，叫优先队列（PriorityQueue））。这种模式借助堆来解决很多这
种前K个数值的问题。**

这个模式是这样的：

* 根据题目要求，将K个元素插入到最小堆或是最大堆。
* 遍历剩下的还没访问的元素，如果当前出来到的这个元素比堆顶元素大，那咱们把堆顶元素先删除，再加当前元素进去。

<a href="https://ibb.co/mXDpgVx"><img src="https://i.ibb.co/nngptNW/12.jpg" alt="12" border="0"></a>

注意这种模式下，咱们不需要去排序数组，因为堆具有这种良好的局部有序性，这对咱们需要解决问题就够了。

识别最大K个元素模式：

* 如果你需要求最大/最小/最频繁的前K个元素
* 如果你需要通过排序去找一个特定的数


**经典题目：**

Top ‘K’ Numbers (easy)

Kth Smallest Number (easy)

‘K’ Closest Points to the Origin (easy)

Connect Ropes (easy)

Top ‘K’ Frequent Numbers (medium)

Frequency Sort (medium)

Kth Largest Number in a Stream (medium)

‘K’ Closest Numbers (medium)

Maximum Distinct Elements (medium)

Sum of Elements (medium)

Rearrange String (hard)
