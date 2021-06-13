
**在二叉树题目选择什么遍历顺序是不少同学头疼的事情,
涉及到二叉树的构造，无论普通二叉树还是二叉搜索树一定前序，都是先构造中节点。
求普通二叉树的属性，一般是后序，一般要通过递归函数的返回值做计算。
求二叉搜索树的属性，一定是中序了，要不白瞎了有序性了。
注意在普通二叉树的属性中，我用的是一般为后序，例如单纯求深度就用前序， 二叉树：找所有路径也用了前序，这是为了方便让父节点指向子节点。
所以求普通二叉树的属性还是要具体问题具体分析**



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
            *  [2.1 二叉树的理论基础](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)
            *  2.2 二叉树类型
               *  [满二叉树](http://data.biancheng.net/view/192.html)
               *  [完全二叉树](http://data.biancheng.net/view/192.html)
               *  [二叉搜索树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)
               *  [平衡二叉搜索树（AVL树）](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)
                  *  [平衡二叉树专题](https://leetcode-solution-leetcode-pp.gitbook.io/leetcode-solution/thinkings/balanced-tree)  
            *  2.3 二叉树存储结构
               *  [二叉树的顺序存储](http://data.biancheng.net/view/193.html)
               *  [二叉树二叉链表存储](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)
               *  二叉树的三叉链表存储
            *  2.4 二叉树的属性
               * [二叉树：是否对称](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484775&idx=1&sn=8acc987b8e87f2f322c26bba47bb4867&scene=21#wechat_redirect)
                 * 递归方法：后序，比较的是根节点的左子树与右子树是不是相互翻转
                 * 迭代方法：使用队列/栈将两个节点顺序放入容器中进行比较 
               * [二叉树：求最大深度](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484791&idx=1&sn=2e9f1308520a74441c66fe60691ce241&scene=21#wechat_redirect)
                 * 递归方法：后序，求根节点最大高度就是最大深度，通过递归函数的返回值做计算树的高度
                 * 迭代方法：层序遍历  
               * [二叉树：求最小深度](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484806&idx=1&sn=a643f2a63896706e0cc12a2db6d4fe85&scene=21#wechat_redirect)
                 * 递归方法：后序，求根节点最小高度就是最小深度，注意最小深度的定义
                 * 迭代方法：层序遍历
               * [二叉树：求有多少个节点](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484827&idx=1&sn=5b784b8814bc971451c86492e74e5fbb&scene=21#wechat_redirect)
                 * 递归方法：后序，通过递归函数的返回值计算节点数量
                 * 迭代方法：层序遍历 
               * [二叉树：是否平衡](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484841&idx=1&sn=fd1380e74ed46c7267b069f3578e2d3a&scene=21#wechat_redirect)
                 * 递归方法：后序，注意后序求高度和前序求深度，递归过程判断高度差
                 * 迭代方法：效率很低，不推荐  
               * [二叉树：找所有路径](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484854&idx=1&sn=bbe5222821da342cae923b1e36bb160c&scene=21#wechat_redirect)
                 * 递归方法：前序，方便让父节点指向子节点，涉及回溯处理根节点到叶子的所有路径
                 * 迭代方法：一个栈模拟递归，一个栈来存放对应的遍历路径 
               * [二叉树：递归中如何隐藏着回溯](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484885&idx=1&sn=590b824ec73eb65de22a7dcc98134d26&scene=21#wechat_redirect)
               * [二叉树：求左叶子之和](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484897&idx=1&sn=fbf25da0459ebaec7cc550109fd106b4&scene=21#wechat_redirect)
                 * 递归方法：后序，必须三层约束条件，才能判断是否是左叶子。
                 * 迭代方法：直接模拟后序遍历 
               * [二叉树：求左下角的值](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484911&idx=1&sn=d493e4c5465aa59192ab58d336e588f9&scene=21#wechat_redirect)
                 * 递归方法：顺序无所谓，优先左孩子搜索，同时找深度最大的叶子节点。
                 * 迭代方法：层序遍历找最后一行最左边 
               * [二叉树：求路径总和](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484927&idx=1&sn=476c0cfc2b04d14fe5c32605a2676b9f&scene=21#wechat_redirect)
                 * 递归方法：顺序无所谓，递归函数返回值为bool类型是为了搜索一条边，没有返回值是搜索整棵树。
                 * 迭代方法：栈里元素不仅要记录节点指针，还要记录从头结点到该节点的路径数值总和 
               * [二叉树：公共祖先问题](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485072&idx=1&sn=1e6c6d28a70ad0f6986ca5f850b74abe&scene=21#wechat_redirect)
                 * 递归：后序，回溯，找到左子树出现目标值，右子树节点目标值的节点。
                 * 迭代：不适合模拟回溯
            *  2.5 二叉树的基本操作
               * [构造二叉树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484950&idx=1&sn=3900f9433d36dd5406fc1ccb1df07703&scene=21#wechat_redirect)
                 * 递归：前序，重点在于找分割点，分左右区间构造
                 * 迭代：比较复杂，意义不大 
               * [构造最大的二叉树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484963&idx=1&sn=f0e1e21dc5cda3e6223ba6e4b46593c7&scene=21#wechat_redirect)
                 * 递归：前序，分割点为数组最大值，分左右区间构造
                 * 迭代：比较复杂，意义不大     
               * [翻转二叉树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484731&idx=1&sn=aa7da461e9c03eb00b3fdbfbfe17e7dc&scene=21#wechat_redirect)
                 * 递归：前序，交换左右孩子
                 * 迭代：直接模拟前序遍历
               * [合并两个二叉树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484988&idx=1&sn=03bc66ed9af4f5ddf7891d06b0a850f3&scene=21#wechat_redirect)
                 * 递归：前序，同时操作两个树的节点，注意合并的规则
                 * 迭代：使用队列，类似层序遍历 
            *  2.6 二叉搜索树的属性
               * [二叉搜索树中的搜索](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485012&idx=1&sn=971ad48e3be136ed9e8d10c1e8a25111&scene=21#wechat_redirect)
                 * 递归：二叉搜索树的递归是有方向的
                 * 迭代：因为有方向，所以迭代法很简单 
               * [是不是二叉搜索树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485028&idx=1&sn=87e2fe177dd794c0c27d57cb1169f3ce&scene=21#wechat_redirect)
                 * 递归：中序，相当于变成了判断一个序列是不是递增的
                 * 迭代：模拟中序，逻辑相同 
               * [求二叉搜索树的最小绝对差](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485040&idx=1&sn=5076aed483d61d710eaf3db626df9c4e&scene=21#wechat_redirect)
                 * 递归：中序，双指针操作
                 * 迭代：模拟中序，逻辑相同
               * [求二叉搜索树的众数](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485055&idx=1&sn=0f3064622d80255348bfec1d8f222dd3&scene=21#wechat_redirect)
                 * 递归：中序，清空结果集的技巧，遍历一遍便可求众数集合
                 * 迭代：模拟中序，逻辑相同 
               * [二叉搜索树转成累加树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485212&idx=1&sn=8f88ae1db8680f906489cbef942f23f8&scene=21#wechat_redirect)
                 * 递归：中序，双指针操作累加
                 * 迭代：模拟中序，逻辑相同
               * [二叉搜索树的公共祖先问题](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485103&idx=1&sn=9cd0d08e1c52497b80c1dea395c63d1d&scene=21#wechat_redirect)
                 * 递归：顺序无所谓，如果节点的数值在目标区间就是最近公共祖先
                 * 迭代：按序遍历 
            *  2.7 二叉搜索树的基本操作
               * [构造二叉搜索树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485194&idx=1&sn=5d28e786feca7c956763269e9ed00f50&scene=21#wechat_redirect)
                 * 递归：前序，数组中间节点分割
                 * 迭代：较复杂，通过三个队列来模拟
               * [二叉搜索树中的插入操作](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485117&idx=1&sn=8f34c86fb6e8adea26189c7beb1ffafc&scene=21#wechat_redirect)
                 * 递归：顺序无所谓，通过递归函数返回值添加节点
                 * 迭代：按序遍历，需要记录插入父节点，这样才能做插入操作 
               * [二叉搜索树中的删除操作](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485135&idx=1&sn=57d1de0ec50e5ccbd4cfd7703de59a8d&scene=21#wechat_redirect)
                 * 递归：前序，想清楚删除非叶子节点的情况
                 * 迭代：有序遍历，较复杂
               * [修剪二叉搜索树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247485155&idx=1&sn=0ceeecc5ca1385049b39a81bedcaecfa&scene=21#wechat_redirect)
                 * 递归：前序，数组中间节点分割
                 * 迭代：较复杂，通过三个队列来模拟   
               * 二叉搜索树的构建 基于数组的构建 插入构建
               * 二叉搜索树的插入 插入到合适位置，插入后仍然是一颗二叉搜索树 递归算法
               * 二叉搜索树的删除(分为删除节点为叶子节点、左子树为空、右子树为空、左右子树均不为空等四个方面，递归算法，删除后仍然是一颗二叉搜索树)
               * 二叉搜索树的搜索 Olgn 递归算法](#二叉搜索树的搜索-Olgn-递归算法
               * 二叉搜索树的遍历，特别是中序遍历 遍历结果为升序序列 递归算法
               * 二叉搜索树的打印 树的前序遍历的应用 递归算法
               * 以广义表形式的字符串构建二叉树
               * 根据二叉树的前序 中序或中序 后序遍历结果构建二叉树
               * 根据二叉树的根结点复制一颗二叉树
               * 二叉树的结点总数
               * 二叉树的根结点、孩子节点的获取
               * 以广义表的形式打印二叉树
               * 判断两颗二叉树是否相等
               * [n个结点构造多少种树](http://data.biancheng.net/view/35.html)
            *  [遍历二叉树](https://www.kancloud.cn/fe_lucifer/leetcode/1996365)
               *  [二叉树的遍历](https://leetcode-solution-leetcode-pp.gitbook.io/leetcode-solution/thinkings/binary-tree-traversal) 
               *  普通二叉树的遍历---如果算法中多次涉及到对二叉树的遍历，普通的二叉树就**需要使用栈结构**做重复性的操作
                  * [深度优先遍历---先往深走，遇到叶子节点再往回走，这里的前中后序，其实指的就是中间节点的遍历顺序，中间节点的顺序就是所谓的遍历方式](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484643&idx=1&sn=a8b3878fe8c72309145acaa50bf8fa4e&scene=21#wechat_redirect)  
                    *  [前序遍历---中左右，中间节点在前](http://data.biancheng.net/view/143.html)
                       * [实现前序遍历的方法一：递归法](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484654&idx=1&sn=0c22c8b8771acc2387bf37ac255749f0&scene=21#wechat_redirect)
                       * [实现前序遍历的方法二：迭代法,借助栈使用非递归的方式来实现  ](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484677&idx=1&sn=e04b4a5baa7a3f6b090947bfa8aea97a&scene=21#wechat_redirect)
                       * [二叉树：前中后序: 迭代法统一风格](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484687&idx=1&sn=85cd297b3c9927467e4048b1f50aa938&scene=21#wechat_redirect)
                    *  [中序遍历---左中右，中间节点在中](http://data.biancheng.net/view/144.html)
                       * [实现中序遍历的方法一：递归法](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484654&idx=1&sn=0c22c8b8771acc2387bf37ac255749f0&scene=21#wechat_redirect)
                       * [实现中序遍历的方法二：迭代法, 借助栈使用非递归的方式来实现  ](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484677&idx=1&sn=e04b4a5baa7a3f6b090947bfa8aea97a&scene=21#wechat_redirect)
                       *  [二叉树：前中后序: 迭代法统一风格](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484687&idx=1&sn=85cd297b3c9927467e4048b1f50aa938&scene=21#wechat_redirect)
                    *  [后序遍历---左右中，中间节点在后](http://data.biancheng.net/view/145.html)
                       * [实现后序遍历的方法一：递归法](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484654&idx=1&sn=0c22c8b8771acc2387bf37ac255749f0&scene=21#wechat_redirect)
                       * [实现后序遍历的方法二：迭代法, 借助栈使用非递归的方式来实现  ](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484677&idx=1&sn=e04b4a5baa7a3f6b090947bfa8aea97a&scene=21#wechat_redirect)
                       * [二叉树：前中后序: 迭代法统一风格](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484687&idx=1&sn=85cd297b3c9927467e4048b1f50aa938&scene=21#wechat_redirect)
                  * 广度优先遍历---一层一层的去遍历
                    *  [广度优先按层遍历](http://data.biancheng.net/view/27.html)
                       * [实现广度优先遍历的方法：使用队列来实现，需要先进先出的结构，才能一层一层的来遍历二叉树 ](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484713&idx=1&sn=2072608d432def7457fdfa27b73d8193&scene=21#wechat_redirect)
               *  [线索二叉树的遍历---线索二叉树**不需要使用栈结构**，在遍历的同时，使用二叉树中空闲的内存空间记录某些结点的前趋和后继元素的位置（不是全部）](http://data.biancheng.net/view/28.html)
                  *  [双向线索二叉树的遍历](http://data.biancheng.net/view/29.html)
            *  排序二叉树
            *  [二叉树：总结篇](https://mp.weixin.qq.com/s/-ZJn3jJVdF683ap90yIj4Q)   
      *  3  平衡二叉树（AVL树）
         *  [平衡二叉树专题](https://leetcode-solution-leetcode-pp.gitbook.io/leetcode-solution/thinkings/balanced-tree)  
      *  [4  B-Tree](https://www.cnblogs.com/dongguacai/p/7239599.html)
      *  5  [红黑树](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247487806&idx=1&sn=0bfb1e78b0297883857958bfe73cd375&chksm=f9a2226fced5ab792d28daf4c7d1ba9a447670de97891d218f257bff8133c86e8c7e3edd43d9&scene=178&cur_album_id=1485825793120387074#rd)
      *  6  特殊树
         * 6.1 区间树
         * [6.2 前缀树---字典树](https://oi-wiki.org/string/trie/)
           * [前缀树](https://leetcode-solution-leetcode-pp.gitbook.io/leetcode-solution/thinkings/trie)
           * [后缀平衡树](https://oi-wiki.org/string/suffix-bst/)
         * 6.3 最小生成树
         * 6.4 树状数组
      *  [8 回文树](https://oi-wiki.org/string/pam/)
      *  [9 哈夫曼树](http://data.biancheng.net/view/33.html)
         * [哈夫曼编码和游程编码](https://leetcode-solution-leetcode-pp.gitbook.io/leetcode-solution/thinkings/run-length-encode-and-huffman-encode)  
      *  [10 并查集](https://oi-wiki.org/ds/dsu/)
         * [并查集应用](https://leetcode-solution-leetcode-pp.gitbook.io/leetcode-solution/thinkings/union-find)  
      *  [11 森林---由 m（m >= 0）个互不相交的树组成的集合被称为森林]()
         *  转换方法
            *  [森林 树和二叉树的转换](http://data.biancheng.net/view/199.html)
            *  树转换为二叉树
            *  二叉树转换树
            *  森林转换为二叉树
            *  二叉树转换森林
            *  树和森林的遍历
      

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
