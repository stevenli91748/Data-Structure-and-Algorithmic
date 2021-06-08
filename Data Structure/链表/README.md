
[几乎刷完了力扣所有的链表题，我发现了这些东西](https://lucifer.ren/blog/2020/11/08/linked-list/)|[链表：总结篇](https://mp.weixin.qq.com/s/vK0JjSTHfpAbs8evz5hH8A)|
---|---|

# 目录

  *  [线性表---LinkList]()
      *  [1 链表的理论基础](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247488536&idx=2&sn=74702c7d7fb54b18199bc50d8e660d6a&scene=21#wechat_redirect)
      *  2 线性表的顺序存储结构
      *  3 线性表的链式存储结构
      *  [4 顺序表和链表优缺点](http://data.biancheng.net/view/162.html)
      *  [静态链表和动态链表的区别](https://blog.csdn.net/zhengqijun_/article/details/78192888#:~:text=%E9%9D%99%E6%80%81%E9%93%BE%E8%A1%A8%E5%92%8C%E5%8A%A8%E6%80%81%E9%93%BE%E8%A1%A8%E6%98%AF%E7%BA%BF%E6%80%A7%E8%A1%A8%E9%93%BE%E5%BC%8F,%E9%A2%84%E5%85%88%E5%88%86%E9%85%8D%E5%9C%B0%E5%9D%80%E7%A9%BA%E9%97%B4%E5%A4%A7%E5%B0%8F%E3%80%82&text=2%E3%80%81%E5%8A%A8%E6%80%81%E9%93%BE%E8%A1%A8%E6%98%AF%E7%94%A8,%E7%9A%84%E9%95%BF%E5%BA%A6%E4%B8%8A%E6%B2%A1%E6%9C%89%E9%99%90%E5%88%B6%E3%80%82)
      *  5 线性表的基本操作
         *  5.1 单链表
            * [链表：听说用虚拟头节点会方便很多？](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484132&idx=1&sn=032d3d00bdfb7179941306a2aa50c9f1&scene=21#wechat_redirect) 
            * [链表的建立](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484144&idx=1&sn=d2783ac63a1e93f7fc7d174308f6b400&scene=21#wechat_redirect)
            * [链表的增加](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484144&idx=1&sn=d2783ac63a1e93f7fc7d174308f6b400&scene=21#wechat_redirect)
            * [链表的删除](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484144&idx=1&sn=d2783ac63a1e93f7fc7d174308f6b400&scene=21#wechat_redirect)
              * [删除链表倒数第N个节点，怎么删](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247488822&idx=2&sn=f431fba72493f4527d379bd077364a54&scene=21#wechat_redirect) 
            * [链表的更改](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484144&idx=1&sn=d2783ac63a1e93f7fc7d174308f6b400&scene=21#wechat_redirect)
            * [链表是否为空](#链表是否为空)
            * [链表的大小](#链表的大小)
            * [链表的打印输出](#链表的打印输出)
            * [删除链表重复节点](#删除链表重复节点)
            * [链表倒数第K个元素](#链表倒数第K个元素)
            * 单链表的反转
              * 双指针法链表的反转
              * 递归法链表的反转
              * [单链表的反转方法一](http://c.biancheng.net/view/8105.html)  
              * [单链表的反转方法二](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484158&idx=1&sn=60a756f681e2edeab28962c70b603ef9&scene=21#wechat_redirect)
            - [链表的倒序输出](#链表的倒序输出)
            - [链表的中间节点](#链表的中间节点)
            - [ 如何判断链表中有环](https://blog.csdn.net/sinat_35261315/article/details/79205157)
            - [链表节点的删除(不知道头结点的情况下](#链表节点的删除不知道头结点的情况下)
            - [ 如何判断两个单链表相交](https://www.nowcoder.com/questionTerminal/db55f7f21127403cb268ffad9d23af37)
              - [链表相交，找出交点](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247488961&idx=2&sn=b14c2e7b54a8e44b0135128978685a8b&scene=21#wechat_redirect) 
            - [链表的交点](#链表的交点)
            - [多项式的列表表示法](#多项式的列表表示法)
            
         *  [5.2 静态链表---StaticLinkList  兼顾了顺序表和链表的优点于一身，可以看做是顺序表和链表的升级版](http://data.biancheng.net/view/163.html)
             
         *  [5.3 双向链表---LinkListDouble](#双向链表)
            -  双向链表的建立
            -  双向链表的节点插入
               - 添加至表头  
               - 添加至表的中间位置
               - 添加至表尾
            -  双向链表的节点删除
         *  [5.4 环链表---LinkListConnect](#环链表)
            - 环型链表的建立
            - 环型链表的节点插入
            - 环型链表的节点删除
            - 环型链表的串联
            - 环型链表表示稀疏矩阵
            - [在链表如何找环，以及如何找环的入口位置](https://mp.weixin.qq.com/s?__biz=MzUxNjY5NTYxNA==&mid=2247484171&idx=1&sn=72ba729f2f4b696dfc4987e232f1ad2d&scene=21#wechat_redirect)
         *  [5.5 双向环链表]()   
      *  6 链栈---LinkStack
      *  7 两栈共享空间---DoubleStack
      *  [8 线性表的分析](#线性表的分析)
         *  [线性表的实现分析](#线性表的实现分析)
         *  [线性表的功能](#线性表的功能)
      * [9 链表：总结篇](https://mp.weixin.qq.com/s/vK0JjSTHfpAbs8evz5hH8A)  

# 内容
---

## 线性表的基本操作
## 线性表的顺序存储结构

      线性表的顺序存储结构比较适合元素个数不太变化，而更多是存取数据的应用
      
      线性表的顺序存储结构的优缺点：
      
      优点：
      
          1. 可快速存取表中任一位置的元素
     
      
      缺点：
      
          1. 插入和删除需要移动大量元素
          
          2. 有存储空间的“碎片”
      
      
      
## 线性表的链式存储结构
### 单链表
单向链表的数据结构及其相关算法：单向链表结构包含两个要素，即头结点head和链表大小size，具体操作包括
#### 链表的建立
#### 链表的增加
#### 链表的删除
#### 链表的更改
#### 链表是否为空
#### 链表的大小
#### 链表的打印输出
#### 删除链表重复节点
#### 链表倒数第K个元素
#### 链表的反转
#### 链表的倒序输出
#### 链表的中间节点
#### 链表是否有环
#### 链表节点的删除不知道头结点的情况下
#### 链表是否相交
#### 链表的交点
#### 多项式的列表表示法

### 静态链表
### 双向链表
### 环链表
## 线性表的分析
### 线性表的实现分析
### 线性表的功能
