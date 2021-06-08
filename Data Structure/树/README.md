
[几乎刷完了力扣所有的树题，我发现了这些东西](https://lucifer.ren/blog/2020/11/23/tree/)|
---|


# 目录

   *  树的概述
      *  1  树的存储结构
         *  树的顺序存储
         *  树的链表存储
         *  树的基本操作
            * [树的双亲表示法](http://data.biancheng.net/view/196.html)
            * [树的孩子表示法](http://data.biancheng.net/view/197.html)
            * [树的孩子兄弟表示法详解](http://data.biancheng.net/view/198.html)
      *  2  [二叉树](http://data.biancheng.net/view/192.html)
            *  [二叉树的理论基础](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)
            *  二叉树类型
               *  [满二叉树](http://data.biancheng.net/view/192.html)
               *  [完全二叉树](http://data.biancheng.net/view/192.html)
               *  [二叉搜索树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)
               *  [平衡二叉搜索树（AVL树）](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)
            *  二叉树存储结构
               *  [二叉树的顺序存储](http://data.biancheng.net/view/193.html)
               *  [二叉树二叉链表存储](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)
               *  二叉树的三叉链表存储
            *  二叉树的基本操作
               * 二叉搜索树的构建 基于数组的构建 插入构建
               * 二叉搜索树的插入 插入到合适位置，插入后仍然是一颗二叉搜索树 递归算法
               * 二叉搜索树的删除(分为删除节点为叶子节点、左子树为空、右子树为空、左右子树均不为空等四个方面，递归算法，删除后仍然是一颗二叉搜索树)
               * 二叉搜索树的搜索 Olgn 递归算法](#二叉搜索树的搜索-Olgn-递归算法
               * 二叉搜索树的遍历，特别是中序遍历 遍历结果为升序序列 递归算法
               * 二叉搜索树的打印 树的前序遍历的应用 递归算法
               * 以广义表形式的字符串构建二叉树
               * 根据二叉树的前序 中序或中序 后序遍历结果构建二叉树
               * 根据二叉树的根结点复制一颗二叉树
               * 二叉树的高度
               * 二叉树的结点总数
               * 二叉树的根结点、孩子节点的获取
               * 以广义表的形式打印二叉树
               * 判断两颗二叉树是否相等
               * [n个结点构造多少种树](http://data.biancheng.net/view/35.html)
            *  [遍历二叉树](https://www.kancloud.cn/fe_lucifer/leetcode/1996365)
               *  普通二叉树的遍历---如果算法中多次涉及到对二叉树的遍历，普通的二叉树就**需要使用栈结构**做重复性的操作
                  * [深度优先遍历---先往深走，遇到叶子节点再往回走，这里的前中后序，其实指的就是中间节点的遍历顺序，中间节点的顺序就是所谓的遍历方式](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)  
                    *  [前序遍历---中左右，中间节点在前](http://data.biancheng.net/view/143.html)
                       * 实现前序遍历的方法一：递归法
                       * 实现前序遍历的方法二：借助栈使用非递归的方式来实现  
                    *  [中序遍历---左中右，中间节点在中](http://data.biancheng.net/view/144.html)
                       * 实现中序遍历的方法一：递归法
                       * 实现中序遍历的方法二：借助栈使用非递归的方式来实现  
                    *  [后序遍历---左右中，中间节点在后](http://data.biancheng.net/view/145.html)
                       * 实现后序遍历的方法一：递归法
                       * 实现后序遍历的方法二：借助栈使用非递归的方式来实现  
                  * 广度优先遍历---一层一层的去遍历
                    *  [广度优先按层遍历](http://data.biancheng.net/view/27.html)
                       * 实现广度优先遍历的方法：使用队列来实现，需要先进先出的结构，才能一层一层的来遍历二叉树 
               *  [线索二叉树的遍历---线索二叉树**不需要使用栈结构**，在遍历的同时，使用二叉树中空闲的内存空间记录某些结点的前趋和后继元素的位置（不是全部）](http://data.biancheng.net/view/28.html)
                  *  [双向线索二叉树的遍历](http://data.biancheng.net/view/29.html)
            *  排序二叉树
            *  [二叉树：总结篇](https://mp.weixin.qq.com/s/-ZJn3jJVdF683ap90yIj4Q)   
      *  3  AVL树
      *  [4  B-Tree](https://www.cnblogs.com/dongguacai/p/7239599.html)
      *  5  红黑树
      *  6  特殊树
         * 6.1 区间树
         * [6.2 字典树](https://oi-wiki.org/string/trie/)
         * 6.3 最小生成树
         * 6.4 树状数组
      *  [7 后缀平衡树](https://oi-wiki.org/string/suffix-bst/)
      *  [8 回文树](https://oi-wiki.org/string/pam/)
      *  [9 哈夫曼树](http://data.biancheng.net/view/33.html)
      *  [10 森林---由 m（m >= 0）个互不相交的树组成的集合被称为森林]()
         *  转换方法
            *  [森林 树和二叉树的转换](http://data.biancheng.net/view/199.html)
      

# 内容

# 树的概述
## 树的存储结构
### 树的链表存储
### 树的基本操作
### 父节点表示法
### 子节点表示法

## 二叉树
二叉树结构包含一个要素，即二叉树的根结点

### 二叉树的基本操作
#### 以广义表形式的字符串构建二叉树
#### 根据二叉树的前序 中序或中序 后序遍历结果构建二叉树
#### 根据二叉树的根结点复制一颗二叉树
#### 二叉树的高度
#### 二叉树的结点总数
#### 二叉树的根结点 孩子节点的获取
#### 以广义表的形式打印二叉树
#### 判断两颗二叉树是否相等

### 二叉树的顺序存储
### 二叉树二叉链表存储
### 二叉树的三叉链表存储

### 遍历二叉树

#### 先序遍历
#### 中序遍历
#### 后序遍历
#### 广度优先按层遍历

### 排序二叉树
二叉搜索树也叫二叉排序树，其中序遍历及时序列的升序排序。此外，二叉搜索树能方便地从中搜索出指定元素
#### 二叉搜索树的构建 基于数组的构建 插入构建
#### 二叉搜索树的插入 插入到合适位置 插入后仍然是一颗二叉搜索树 递归算法
#### 二叉搜索树的删除
#### 二叉搜索树的搜索 Olgn 递归算法
#### 二叉搜索树的遍历 特别是中序遍历 遍历结果为升序序列 递归算法
#### 二叉搜索树的打印 树的前序遍历的应用 递归算法

### 红黑树

## 森林
## 转换方法
### 森林 树和二叉树的转换
## 哈夫曼树
### 哈夫曼树的概念
