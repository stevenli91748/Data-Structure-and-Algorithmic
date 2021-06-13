
[双指针法：总结篇！](https://mp.weixin.qq.com/s/_p7grwjISfMh0U65uOyCjA)|[双指针](https://leetcode-solution-leetcode-pp.gitbook.io/leetcode-solution/91/two-pointers)|
---|

---

<a href="https://ibb.co/6DYzF4M"><img src="https://i.ibb.co/2cqxdj9/two-point.jpg" alt="two-point" border="0"></a>

**双指针是这样的模式：两个指针朝着左右方向移动（双指针分为同向双指针和异向双指针），直到他们有一个或是两个都满足某种条件。双指针通常用在排好序的数组或是链表中寻找对子。比如，你需要去比较数组中每个元素和其他元素的关系时，你就需要用到双指针了。我们需要双指针的原因是：如果你只用一个指针的话，你得来回跑才能在数组中找到你需要的答案。这一个指针来来回回的过程就很耗时和浪费空间了 — 这是考虑算法的复杂度分析的时候的重要概念。虽然brute force一个指针的解法可能会奏效，但时间复杂度一般会是O(n²)。在很多情况下，双指针能帮助我们找到空间或是时间复杂度更低的解。**


识别使用双指针的招数：

* 一般来说，数组或是链表是排好序的，你得在里头找一些组合满足某种限制条件
* 这种组合可能是一对数，三个数，或是一个子数组


**经典题目：**

Pair with Target Sum (easy)

Remove Duplicates (easy)

Squaring a Sorted Array (easy)

Triplet Sum to Zero (medium)

Triplet Sum Close to Target (medium)

Triplets with Smaller Sum (medium)

Subarrays with Product Less than a Target (medium)

Dutch National Flag Problem (medium)
