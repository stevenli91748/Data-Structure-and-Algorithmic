
# LeetCode 
* [0. 高频题](#0-高频题)
* [1. 基础篇](#1-基础篇)
  * [1.1 数据结构部分 ](#1A-数据结构部分)
  * [1.2 算法部分](#1B-算法部分)
* [2. 进阶篇](#2-进阶篇)
* [3. 专题篇](#3-专题篇)
  * [3.1 经典题型分类](#3A-经典题型分类)
* [4. 公司篇](#4-公司篇)

---
# 怎样刷leetCode
  * [土妹刷leetCode系列](https://www.youtube.com/watch?v=d6XqH991bB8&list=PLeRPcJf8vjt1LPbXt7xfJ7Sv-6B57F3IV&index=2)

# 0-高频题

# 1 基础篇
## 1A 数据结构部分
   * 位操作
   * 数学
   * 线性结构
     * 栈 Stack
     * 队列 Queue
     * 链表 Linked List 
     * 数组 Array
     * 字符串处理
   * 非线性结构 
     * 哈希表 Hash Table
     * 矩阵（二维或多维数组） 
     * 堆 Heap
       * 二叉堆
     * [树](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E9%83%A8%E5%88%86/LeetCode---%E6%A0%91%20tree.md)
       * [二叉树](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E9%83%A8%E5%88%86/%E4%BA%8C%E5%8F%89%E6%A0%91.md)
       * 四叉树
       * 八叉树
       * k-d树(k维的树结构)
       * 二叉搜索树
       * 二叉平衡树
       * AVL(高度平衡树)
       * 红黑树
       * 并查集
       * 特殊树
         * 树状数组
         * 字典树 Trie（前缀树）
           * [316 去除重复字母(困难)---Remove Duplicate Letters](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/316%20%E5%8E%BB%E9%99%A4%E9%87%8D%E5%A4%8D%E5%AD%97%E6%AF%8D(%E5%AD%97%E5%85%B8%E6%A0%91%20%E5%9B%B0%E9%9A%BE)---Remove%20Duplicate%20Letters.md)
           * [321 拼接最大数(困难)---Create Maximum Number](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/321%20%E6%8B%BC%E6%8E%A5%E6%9C%80%E5%A4%A7%E6%95%B0(%E5%AD%97%E5%85%B8%E6%A0%91%20%E5%9B%B0%E9%9A%BE)---Create%20Maximum%20Number.md)
           * [402 移掉 K 位数字(中等)---Remove K Digits](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/402%20%E7%A7%BB%E6%8E%89%20K%20%E4%BD%8D%E6%95%B0%E5%AD%97(%E5%AD%97%E5%85%B8%E6%A0%91%20%E4%B8%AD%E7%AD%89)---Remove%20K%20Digits.md)
           * [1081 不同字符的最小子序列（中等）---Smallest Subsequence of Distinct Characters ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/1081%20%E4%B8%8D%E5%90%8C%E5%AD%97%E7%AC%A6%E7%9A%84%E6%9C%80%E5%B0%8F%E5%AD%90%E5%BA%8F%E5%88%97%EF%BC%88%E5%AD%97%E5%85%B8%E6%A0%91%20%E4%B8%AD%E7%AD%89%EF%BC%89---Smallest%20Subsequence%20of%20Distinct%20Characters%20.md)
         * 线段树
     * 图
       * 最短路径
       * 最小生成树 
       * 并查集 Union Find
     * 图形
       * 点
       * 线
       * 面

## 1B 算法部分
   * 1B.1 基础算法
     * 枚举算法
     * 模拟算法
     * 分治算法 Divide Conquer 
     * 二分搜索算法 Binary Search 
     * 贪心算法 
     * 前缀和 & 差分算法
     * 倍增算法
     * 构造算法
   * 1B.2 排序算法
     * 内部排序 只使用内存 
       * 插入排序
         * 直接插入排序
         * 折半插入排序
         * 希尔排序
       * 选择排序
         * 简单选择排序
       * 堆排序
       * 快速排序
       * 冒泡排序
       * 归并排序
       * 桶式排序
       * 基数排序
       * 计数排序 
       * 快排 Quick Sort
     * 外部排序 内存和外存结合使用
       * [外存信息的存取](#外存信息的存取)
       * [外部排序的方法](#外部排序的方法)
       * [多路平衡归并的实现](#多路平衡归并的实现)
       * [置换选择排序](#置换选择排序)
       * [最佳归并树](#最佳归并树)
   * 1B.3 查找算法
     * 数据结构中的查找算法
       * 顺序表结构中的查找算法	
       * 链表结构中的查找算法	
       * 树结构中的查找算法	
       * 图结构中的查找算法 
     * 回溯法 Backtracking
       * 排列
       * 子集
       * 组合 
     * 插值查找算法
     * 递归算法 
     * 奜波那契(黄金分割法)查找算法
     * 宽度优先搜索算法 Breadth First Search 
     * 深度优先搜索算法 Depth First Search
     * [线性索引查找](#线性索引查找)
     * [多路查找树B树](#多路查找树B树)
     * 平衡二叉数算法
     * [静态查找表](#静态查找表)
       *  [顺序表查找](#顺序表查找)
       *  [有序表查找](#有序表查找)
       *  [静态树表的查找](#静态树表的查找)
       *  [索引顺序表的查找](#索引顺序表的查找)
     * [动态查找表](#动态查找表)
       *  [键树](#键树)     
       *  [B_树和B+树](#B_树和B+树)
       *  [二叉排序树](#二叉排序树)
   * 1B.4 双指针 Two Pointers 
   * 1B.5 动态规划 Dynamic Programming
     * 背包问题
     * 最长子序列  
   * 1B.6 扫描线 Scan-line algorithm
   

# 2 进阶篇
  *  Trie
  *  KMP & RK
  *  跳表
  *  剪枝
  *  高频面试题

# 3 专题篇
## 3A 经典题型分类

* [1 Pattern: Sliding Window---滑动窗口类型](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/1.%20Pattern:%20Sliding%20window%EF%BC%8C%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3%E7%B1%BB%E5%9E%8B/README.md)
* [2 Pattern: Two Pointers---双指针类型](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/2%20Pattern:%20Two%20Pointers/README.md)
* [3 Pattern: Fast & Slow pointers---快慢指针类型](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/3.%20Pattern:%20Fast%20%26%20Slow%20pointers%2C%20%E5%BF%AB%E6%85%A2%E6%8C%87%E9%92%88%E7%B1%BB%E5%9E%8B/README.md)
* [4 Pattern: Merge Intervals---区间合并类型](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/4.%20Pattern:%20Merge%20Intervals%EF%BC%8C%E5%8C%BA%E9%97%B4%E5%90%88%E5%B9%B6%E7%B1%BB%E5%9E%8B/README.md)
* [5 Pattern: Cyclic Sort---循环排序](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/5.%20Pattern:%20Cyclic%20Sort%EF%BC%8C%E5%BE%AA%E7%8E%AF%E6%8E%92%E5%BA%8F/README.md)
* [6 Pattern: In-place Reversal of a LinkedList---链表翻转](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/6.%20Pattern:%20In-place%20Reversal%20of%20a%20LinkedList%EF%BC%8C%E9%93%BE%E8%A1%A8%E7%BF%BB%E8%BD%AC/README.md)
* [7 Pattern: Tree Breadth First Search---树上的BFS](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/7.%20Pattern:%20Tree%20Breadth%20First%20Search%EF%BC%8C%E6%A0%91%E4%B8%8A%E7%9A%84BFS/README.md)
* [8 Pattern: Tree Depth First Search---树上的DFS](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/8.%20Pattern:%20Tree%20Depth%20First%20Search%EF%BC%8C%E6%A0%91%E4%B8%8A%E7%9A%84DFS/README.md)
* [9 Pattern: Two Heaps---双堆类型](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/9.%20Pattern:%20Two%20Heaps%EF%BC%8C%E5%8F%8C%E5%A0%86%E7%B1%BB%E5%9E%8B/README.md)
* [10 Pattern: Subsets---子集类型，一般都是使用多重DFS](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/10.%20Pattern:%20Subsets%EF%BC%8C%E5%AD%90%E9%9B%86%E7%B1%BB%E5%9E%8B%EF%BC%8C%E4%B8%80%E8%88%AC%E9%83%BD%E6%98%AF%E4%BD%BF%E7%94%A8%E5%A4%9A%E9%87%8DDFS/README.md)
* [11 Pattern: Modified Binary Search---改造过的二分](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/11.%20Pattern:%20Modified%20Binary%20Search%EF%BC%8C%E6%94%B9%E9%80%A0%E8%BF%87%E7%9A%84%E4%BA%8C%E5%88%86/README.md)
* [12 Pattern: Top 'K' Elements---前K个系列](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/12.%20Pattern:%20Top%20%E2%80%98K%E2%80%99%20Elements%EF%BC%8C%E5%89%8DK%E4%B8%AA%E7%B3%BB%E5%88%97/README.md)
* [13 Pattern: K-way merge---多路归并](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/13.%20Pattern:%20K-way%20merge%EF%BC%8C%E5%A4%9A%E8%B7%AF%E5%BD%92%E5%B9%B6/README.md)
* [14 Pattern : 0/1 Knapsack (Dynamic Programming)---0/1背包类型](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/14.%20Pattern:%200%20mod%201%20Knapsack%20(Dynamic%20Programming)/README.md)
* [15 Pattern: Topological Sort (Graph)---拓扑排序类型](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/%E7%BB%8F%E5%85%B8%E9%A2%98%E5%9E%8B%E5%88%86%E7%B1%BB/15.%20Pattern:%20Topological%20Sort%20(Graph)%EF%BC%8C%E6%8B%93%E6%89%91%E6%8E%92%E5%BA%8F%E7%B1%BB%E5%9E%8B/README.md)
* 日程安排专题
  * [252 会议室（easy）---Meeting Rooms  ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/252%20%E4%BC%9A%E8%AE%AE%E5%AE%A4%EF%BC%88easy%EF%BC%89---Meeting%20Rooms.md)
  * [253 会议室 II(Medium)---	Meeting Rooms II   ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/253%20%E4%BC%9A%E8%AE%AE%E5%AE%A4%20II(Medium)---%09Meeting%20Rooms%20II%20%20%20.md)
  * [729 我的日程安排表 I(Medium)---My Calendar I   ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/729%20%E6%88%91%E7%9A%84%E6%97%A5%E7%A8%8B%E5%AE%89%E6%8E%92%E8%A1%A8%20I(Medium)---My%20Calendar%20I.md)
  * [731 我的日程安排表 II(Medium)---My Calendar II  ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/731%20%E6%88%91%E7%9A%84%E6%97%A5%E7%A8%8B%E5%AE%89%E6%8E%92%E8%A1%A8%20II(Medium)---My%20Calendar%20II%20.md)
  * [732 我的日程安排表 III(Hard)---My Calendar III   ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/732%20%E6%88%91%E7%9A%84%E6%97%A5%E7%A8%8B%E5%AE%89%E6%8E%92%E8%A1%A8%20III(Hard)---My%20Calendar%20III%20%20.md)
* 16 二分法
* 17 Pattern: Bitwise XOR

# 4 公司篇
  
  *  [公司篇汇总](https://leetcode.jp/problems.php)
  

