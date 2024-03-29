
| **[数组理论知识](#数组理论知识) ** |  | 
| :--- | :---: | 
| **[数组的经典题目--解题思想](#数组的经典题目)** |  | 
| :--- | :---: | 
| 1   **数组是一种顺序存储结构，能存储线性结构和非线性结构**| [无代码] |
| 1-1-0 稀疏数组| |
| 1-1-0 [环形数组(CircularArray)](https://blog.csdn.net/sinat_36246371/article/details/78836336)||
| 1-1-0 [后缀数组](https://oi-wiki.org/string/sa/)||
| 1-1-0 [广义表](http://data.biancheng.net/view/190.html)||
| 1-1-1 数组模拟队列||
| 1-1-2 数组模拟环型队列||
| 1-1-5 用数组实现链表结构代码|[无代码]|
| ---    用数组实现链表结构的时间复杂度||
| 1-1-6 用数组实现树结构代码| [无代码]|
| ---    用数组实现树结构时间复杂度| [无代码]|
| 1-1-7 用数组实现图结构代码| [无代码]|
|---     用数组实现图结构时间复杂度| [无代码]|
| 2  **数组的操作** | [无代码] |
| 2-1 **一维数组的操作**| [无代码] |
| 2-1-1  数组元素的查找操作 | [无代码] |
| 2-1-2  数组元素的增加操作 | [无代码] |
| 2-1-2-1  顺序存储结构的增加操作||
| 2-1-2-1-1  插入到顺序表的表头||
| 2-1-2-1-2  在顺序表的中间位置插入元素||
| 2-1-2-1-3  在顺序表中的最后位置插入元素||
| 2-1-2-2  链式存储结构的增加操作||
| 2-1-2-2-1  插入到链式存储结构的表头||
| 2-1-2-2-2  在链式存储结构的中间位置插入元素||
| 2-1-2-2-3  在链式存储结构的最后位置插入元素||
| 2-1-3  数组元素的更新操作 | [无代码] |
| 2-1-3-1  顺序存储结构的更新操作||
| 2-1-3-2  链式存储结构的更新操作||
| 2-1-4  数组元素的删除操作 | [无代码] |
| 2-1-4-1  顺序存储结构的删除操作||
| 2-1-4-2  链式存储结构的删除操作||
| 2-2  **二维数组(矩阵)的操作** | [无代码] |
| 2-2-1   矩阵类型||
| 2-2-1-1 [对称矩阵](http://data.biancheng.net/view/183.html)||
| 2-2-1-2 [上（下）三角矩阵](http://data.biancheng.net/view/183.html) ||
| 2-2-1-3 [稀疏矩阵](http://data.biancheng.net/view/183.html) ||
| 2-2-1   矩阵操作||
| 2-2-1 矩阵相加| [无代码] |
| 2-2-1 矩阵相乘| [无代码] |
| 2-2-1 转置矩阵| [无代码] |
| 3  **优化数组的存储方式**| [无代码] |
| 3-1 [将多维数组存储在一维内存空间的存储方式](http://data.biancheng.net/view/182.html)| [无代码] |
| 3-1 二维数组(矩阵)的存储方式|[无代码] |
| 3-1-1  规则矩阵压缩代码| [无代码] |
|[二维数组的地址分布究竟是什么样的](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247487411&idx=2&sn=f36c6a5364a976b36f3d6eb22d1d9195&chksm=f9a23ce2ced5b5f4db53d9a5d577364a1ce6eebfd3e3489f2573ee9f8133fdf199f398bc8daa&scene=178&cur_album_id=1485825793120387074#rd)||
| 3-1-2  稀疏矩阵压缩存储（3种方式）| [无代码] |
| 3-1-2  1. [三元组顺序表](http://data.biancheng.net/view/184.html) ||
| 3-1-2  2. [行逻辑链接的顺序表](http://data.biancheng.net/view/185.html)||
| 3-1-2  3. [十字链表](http://data.biancheng.net/view/186.html)||
| 3-1-3  01矩阵压缩代码| [无代码] |
| 4  **数组排序与顺序统计**| [无代码] |
| 5  **数组的查找**  ||
| 5-1 线性查找||
| 5-2 二分查找||


## 数组理论知识

  [程序员算法面试中，必须掌握的数组理论知识](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247483956&idx=1&sn=2e63f2ed9d6711fb3485533c178a4ad0&scene=21#wechat_redirect)|
  ---|

   <a href="https://ibb.co/cLx9FP8"><img src="https://i.ibb.co/DpLFCNM/array.png" alt="array" border="0"></a>
 
  
   一维数组是存放在连续内存空间上的相同类型数据的集合，二维数组其实就是一个矩阵，二位数组中其实是一个线性数组存放着 其他数组的首地址，所以二维数据在内存中array[3][4]不是 3*4 的连续地址空间，
   而是四条连续的地址空间组成
  
## [数组的经典题目](https://mp.weixin.qq.com/s/LIfQFRJBH5ENTZpvixHEmg)
   
   1. 二分法思想： [数组：每次遇到二分法，都是一看就会，一写就废](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484289&idx=1&sn=929fee0ac9f308a863a4fc4e2e44506e&scene=21#wechat_redirect)
   2. 双指针法思想: [数组：就移除个元素很难么？](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484304&idx=1&sn=ad2e11d171f74ad772fd23b10142e3f3&scene=21#wechat_redirect)
   3. 滑动窗口思想: [数组：滑动窗口拯救了你](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484315&idx=1&sn=414b885abba34abfd8d9f35c9f61b857&scene=21#wechat_redirect)
   4. 模拟行为思想: [数组：这个循环可以转懵很多人！](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484331&idx=1&sn=dc41b2ba53227743f6a1b0433f9db6ef&scene=21#wechat_redirect)




# 参考

程序设计中实用的数据结构.pdf

图解数据结构.pdf
