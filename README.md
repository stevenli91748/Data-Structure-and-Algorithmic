# Data-Structure-and-Algorithmic

# [数据结构与算法面试](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/tree/master/Interview)

#  [数据结构和算法的学习方法路径](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E5%AD%A6%E4%B9%A0%E6%96%B9%E6%B3%95.md)

# 目录
---

##  数据结构
   *  [数组](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E6%95%B0%E7%BB%84.md)
   *  [集合](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E9%9B%86%E5%90%88.md)
   *  [线性表](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E7%BA%BF%E6%80%A7%E8%A1%A8.md)
      *  线性表的基本操作
      *  线性表的顺序存储结构
      *  线性表的链式存储结构
         *  单链表
         *  静态链表
         *  双向链表
         *  环链表
      *  线性表的分析
         *  线性表的实现分析
         *  线性表的功能
   *  栈与队列
       * [栈](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E6%A0%88.md)
         *  栈的常用操作
         *  栈的顺序存储结构
         *  栈的链式存储结构
         *  两栈共享空间
         *  Java集合中的栈
       * [队列](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E9%98%9F%E5%88%97.md)
          *  队列的常用操作
          *  队列的顺序存储结构
          *  队列的链式存储结构
          *  环队列
          *  Java集合中的队列
      *  双端队列
   *  [堆](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E5%A0%86.md)
   *  [散列](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E6%95%A3%E5%88%97.md)
      *  散列的概念
   *  [串](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E4%B8%B2.md)
      *  串的存储结构
   *  [树](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E6%A0%91.md)
      *  树的概述
         *  树的存储结构 
            *  树的链表存储
         *  树的基本操作
         *  父节点表示法
         *  子节点表示法
      *  二叉树
         *  二叉树的基本操作
         *  二叉树的顺序存储
         *  二叉树二叉链表存储
         *  二叉树的三叉链表存储
         *  遍历二叉树
            *  先序遍历
            *  中序遍历
            *  后序遍历
            *  广度优先（按层）遍历
         *  排序二叉树
         *  红黑树
      *  森林
      *  转换方法
         *  森林 树和二叉树的转换
      *  哈夫曼树
         *  哈夫曼树的概念
         
   *  [图](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/%E5%9B%BE.md)
      *  图的存储结构
      *  图的遍历
   *  [排序](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Algorithmic/%E6%8E%92%E5%BA%8F%E7%AE%97%E6%B3%95.md)
   * [内部排序 只使用内存](#内部排序-只使用内存)
     *  [插入排序](#插入排序)
        *  [直接插入排序](#直接插入排序)
           * [直接插入排序 算法基本思想](#直接插入排序-算法基本思想)
           * [直接插入排序 算法的时间复杂度](#直接插入排序-算法的时间复杂度)
           * [直接插入排序 算法的空间复杂度](#直接插入排序-算法的空间复杂度)
           * [直接插入排序 算法的稳定性](#直接插入排序-算法的稳定性)
       *  [折半插入排序](#折半插入排序)
           * [折半插入排序 算法基本思想](#折半插入排序-算法基本思想)
           * [折半插入排序 算法的时间复杂度](#折半插入排序-算法的时间复杂度)
           * [折半插入排序 算法的空间复杂度](#折半插入排序-算法的空间复杂度)
           * [折半插入排序 算法的稳定性](#折半插入排序-算法的稳定性)
       *  [希尔排序](#希尔排序)
           * [希尔排序 算法基本思想](#希尔排序-算法基本思想)
           * [希尔排序 算法的时间复杂度](#希尔排序-算法的时间复杂度)
           * [希尔排序 算法的空间复杂度](#希尔排序-算法的空间复杂度)
           * [希尔排序 算法的稳定性](#希尔排序-算法的稳定性)
     
   *  [选择排序](#选择排序)
      *  [简单选择排序](#简单选择排序)
         * [简单选择排序 算法基本思想](#简单选择排序-算法基本思想)
         * [简单选择排序 算法的时间复杂度](#简单选择排序-算法的时间复杂度)
         * [简单选择排序 算法的空间复杂度](#简单选择排序-算法的空间复杂度)
         * [简单选择排序 算法的稳定性](#简单选择排序-算法的稳定性)
      
      *  [堆排序](#堆排序)
         * [堆排序 算法基本思想](#堆排序-算法基本思想)
         * [堆排序 算法的时间复杂度](#堆排序-算法的时间复杂度)
         * [堆排序 算法的空间复杂度](#堆排序-算法的空间复杂度)
         * [堆排序 算法的稳定性](#堆排序-算法的稳定性)
      
   *  [交换排序](#交换排序)
      *  [冒泡排序](#冒泡排序)
         * [冒泡排序 算法基本思想](#冒泡排序-算法基本思想)
         * [冒泡排序 算法的时间复杂度](#冒泡排序-算法的时间复杂度)
         * [冒泡排序 算法的空间复杂度](#冒泡排序-算法的空间复杂度)
         * [冒泡排序 算法的稳定性](#冒泡排序-算法的稳定性)
      
      *  [快速排序](#快速排序)
         * [快速排序 算法基本思想](#快速排序-算法基本思想)
         * [快速排序 算法的时间复杂度](#快速排序-算法的时间复杂度)
         * [快速排序 算法的空间复杂度](#快速排序-算法的空间复杂度)
         * [快速排序 算法的稳定性](#快速排序-算法的稳定性)
      
   *  [归并排序](#归并排序)
         * [归并排序 算法基本思想](#归并排序-算法基本思想)
         * [归并排序 算法的时间复杂度](#归并排序-算法的时间复杂度)
         * [归并排序 算法的空间复杂度](#归并排序-算法的空间复杂度)
         * [归并排序 算法的稳定性](#归并排序-算法的稳定性)

   *  [桶式排序](#桶式排序)
         * [桶式排序 算法基本思想](#桶式排序-算法基本思想)
         * [桶式排序 算法的时间复杂度](#桶式排序-算法的时间复杂度)
         * [桶式排序 算法的空间复杂度](#桶式排序-算法的空间复杂度)
         * [桶式排序 算法的稳定性](#桶式排序-算法的稳定性)
   
   *  [基数排序](#基数排序)
         * [基数排序 算法基本思想](#基数排序-算法基本思想)
         * [基数排序 算法的时间复杂度](#基数排序-算法的时间复杂度)
         * [基数排序 算法的空间复杂度](#基数排序-算法的空间复杂度)
         * [基数排序 算法的稳定性](#基数排序-算法的稳定性)
   
  * [外部排序 内存和外存结合使用](#外部排序-内存和外存结合使用)
         * [外存信息的存取](#外存信息的存取)
         * [外部排序的方法](#外部排序的方法)
         * [多路平衡归并的实现](#多路平衡归并的实现)
         * [置换选择排序](#置换选择排序)
         * [最佳归并树](#最佳归并树)



   *  [查找](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Algorithmic/%E6%9F%A5%E6%89%BE.md)
      *  [静态查找表](#静态查找表)
         *  [顺序表查找](#顺序表查找)
         *  [有序表查找](#有序表查找)
         *  [静态树表的查找](#静态树表的查找)
         *  [索引顺序表的查找](#索引顺序表的查找)
      *  [动态查找表](#动态查找表)
         *  [键树](#键树)     
         *  [B_树和B+树](#B_树和B+树)
         *  [二叉排序树](#二叉排序树)
      *  [哈希表](#哈希表)   
      *  [平衡二叉数](#平衡二叉数)
      *  [线性索引查找](#线性索引查找)
      *  [多路查找树B树](#多路查找树B树)
      *  [散列表查找](#散列表查找)




##  算法
## [算法的学习方法](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Algorithmic/%E7%AE%97%E6%B3%95%E5%AD%A6%E4%B9%A0%E6%96%B9%E6%B3%95.md)
   
   *  算法策略
   *  算法分析
      *  算法效能分析
         *  时间复杂度
         *  Big-oh
         *  omega
         *  theta
   *  算法设计
      *  贪心算法
      *  分而治之策略
      *  动态规划
      *  修剪与搜索法
      *  树搜索法
      *  问题转换法
      *  图算法
      *  计算几何法
      *  网络流
      *  近拟算法
      *  随机算法
      
      
     
      
      
#  参考书籍
   * [算法与数据结构+一点点ACM从入门到进阶吐血整理推荐书单（珍藏版）](https://pymlovelyq.github.io/2018/10/06/Algorithm/)
   *  Java程序员的基本修养---疯狂Java讲义
   *  [从入门到修仙的算法之路](https://mp.weixin.qq.com/s?__biz=MzI5MzYzMDAwNw==&mid=2247484319&idx=1&sn=11f9bce35fae40dd2ed54b2b3c785425&chksm=ec6e7ac7db19f3d14c11cd9e6e03f4ef2d31d45332979cf44711f15213dd964d8ced00643260&token=516051101&lang=zh_CN#rd)
   *  https://github.com/githubofrico
   *  [可视化的数据结构 - 各种算法动画演示](https://visualgo.net/en)
   *  [Algomation：查看、创建和分享算法的学习平台](http://hao.jobbole.com/algomation/)
   *  [ Algorithm Visualizer，做得很好](https://algorithm-visualizer.org/divide-and-conquer/bucket-sort)
   *  [[数据结构与算法]超级详细解读基本排序算法（不看后悔，带排序演示动画）](https://blog.csdn.net/david_520042/article/details/52784620)
   * [剖析八种经典排序算法](https://blog.csdn.net/l953972252/article/details/51284884)
   * [Leetcode 简略题解 - 共567题](https://zhuanlan.zhihu.com/p/25697275)
   * [leetcode题解](https://mp.weixin.qq.com/s/vG0URwp8gI4jOkZlG5Vp6g)
   * [https://github.com/zhuli19901106/leetcode-2](https://github.com/zhuli19901106/leetcode-2)
   * [看动画学算法](https://github.com/MisterBooo/LeetCodeAnimation)
   
