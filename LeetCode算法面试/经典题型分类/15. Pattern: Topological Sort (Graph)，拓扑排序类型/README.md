拓扑排序模式用来寻找一种线性的顺序，这些元素之间具有依懒性。比如，如果事件B依赖于事件A，那A在拓扑排序顺序中排在B的前面。

这种模式定义了一种简单方式来理解拓扑排序这种技术。

这种模式是这样奏效的：

初始化
a) 借助于HashMap将图保存成邻接表形式。
b) 找到所有的起点，用HashMap来帮助记录每个节点的入度
创建图，找到每个节点的入度
a) 利用输入，把图建好，然后遍历一下图，将入度信息记录在HashMap中
找所有的起点
a) 所有入度为0的节点，都是有效的起点，而且我们讲他们都加入到一个队列中
排序
a) 对每个起点，执行以下步骤
—i) 把它加到结果的顺序中
— ii)将其在图中的孩子节点取到
— iii)将其孩子的入度减少1
— iv)如果孩子的入度变为0，则改孩子节点成为起点，将其加入队列中
b) 重复（a）过程，直到起点队列为空。


<a href="https://ibb.co/Q6jwsFh"><img src="https://i.ibb.co/qRFQbMh/15.jpg" alt="15" border="0"></a>


拓扑排序模式识别：

* 待解决的问题需要处理无环图
* 你需要以一种有序的秩序更新输入元素
* 需要处理的输入遵循某种特定的顺序

**经典题目：**

Topological Sort (medium)

Tasks Scheduling (medium)

Tasks Scheduling Order (medium)

All Tasks Scheduling Orders (hard)

Alien Dictionary (hard)
