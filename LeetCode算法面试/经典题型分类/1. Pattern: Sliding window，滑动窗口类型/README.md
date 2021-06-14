
[滑动窗口（思路 + 模板）](https://www.kancloud.cn/fe_lucifer/leetcode/1996373)|
---|

---

<a href="https://ibb.co/Hzxc3rF"><img src="https://i.ibb.co/KqLtS90/sliding-window.jpg" alt="sliding-window" border="0"></a>


**滑动窗口类型的题目经常是用来执行数组或是链表上某个区间（窗口）上的操作。比如找最长的全为1的子数组长度。滑动窗口一般从第一个元素开始，一直往右边一个一个元素挪动。当然了，根据题目要求，我们可能有固定窗口大小的情况，也有窗口的大小变化的情况**

下面是一些我们用来判断我们可能需要上滑动窗口策略的方法：

* 这个问题的输入是一些线性结构：比如链表呀，数组啊，字符串啊之类的
* 让你去求最长/最短子字符串或是某些特定的长度要求

**经典题目：**
* [一文带你 AC 十道题【滑动窗口】](https://lucifer.ren/blog/2020/03/16/slide-window/)
* [3	无重复字符的最长子串---Longest Substring Without Repeating Characters     ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/3%20%E6%97%A0%E9%87%8D%E5%A4%8D%E5%AD%97%E7%AC%A6%E7%9A%84%E6%9C%80%E9%95%BF%E5%AD%90%E4%B8%B2(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Longest%20Substring%20Without%20Repeating%20Characters.md)
* [76. 最小覆盖子串---Minimum Window Substring    ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/76.%20%E6%9C%80%E5%B0%8F%E8%A6%86%E7%9B%96%E5%AD%90%E4%B8%B2(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Minimum%20Window%20Substring%20.md)
* [159 至多包含两个不同字符的最长子串---Longest Substring with At Most Two Distinct Characters  ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/159%20%E8%87%B3%E5%A4%9A%E5%8C%85%E5%90%AB%E4%B8%A4%E4%B8%AA%E4%B8%8D%E5%90%8C%E5%AD%97%E7%AC%A6%E7%9A%84%E6%9C%80%E9%95%BF%E5%AD%90%E4%B8%B2(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Longest%20Substring%20with%20At%20Most%20Two%20Distinct%20Characters.md)
* [209 长度最小的子数组(滑动窗口 中等) ---Minimum Size Subarray Sum](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/209%20%E9%95%BF%E5%BA%A6%E6%9C%80%E5%B0%8F%E7%9A%84%E5%AD%90%E6%95%B0%E7%BB%84(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3%20%E4%B8%AD%E7%AD%89)%20---Minimum%20Size%20Subarray%20Sum.md)
* [239 滑动窗口最大值 ---Sliding Window Maximum ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/239%20%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3%E6%9C%80%E5%A4%A7%E5%80%BC%20---Sliding%20Window%20Maximum%20.md)
* [438. 找到字符串中所有字母异位词---Find All Anagrams in a String ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/438.%20%E6%89%BE%E5%88%B0%E5%AD%97%E7%AC%A6%E4%B8%B2%E4%B8%AD%E6%89%80%E6%9C%89%E5%AD%97%E6%AF%8D%E5%BC%82%E4%BD%8D%E8%AF%8D(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Find%20All%20Anagrams%20in%20a%20String%20.md)
* [467. 环绕字符串中唯一的子字符串(中等)---Unique Substrings in Wraparound String    ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/467.%20%E7%8E%AF%E7%BB%95%E5%AD%97%E7%AC%A6%E4%B8%B2%E4%B8%AD%E5%94%AF%E4%B8%80%E7%9A%84%E5%AD%90%E5%AD%97%E7%AC%A6%E4%B8%B2(%20%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3%20%E4%B8%AD%E7%AD%89)---Unique%20Substrings%20in%20Wraparound%20String.md)
* [795. 区间子数组个数(滑动窗口 中等)---Number of Subarrays with Bounded Maximum](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/795.%20%E5%8C%BA%E9%97%B4%E5%AD%90%E6%95%B0%E7%BB%84%E4%B8%AA%E6%95%B0(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3%20%E4%B8%AD%E7%AD%89)---Number%20of%20Subarrays%20with%20Bounded%20Maximum%20%20.md)
* [862 和至少为 K 的最短子数组  ---Shortest Subarray with Sum at Least K](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/862%20%E5%92%8C%E8%87%B3%E5%B0%91%E4%B8%BA%20K%20%E7%9A%84%E6%9C%80%E7%9F%AD%E5%AD%90%E6%95%B0%E7%BB%84(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)%20%20---Shortest%20Subarray%20with%20Sum%20at%20Least%20K.md)
* [904. 水果成篮---Fruit Into Baskets    ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/904.%20%E6%B0%B4%E6%9E%9C%E6%88%90%E7%AF%AE(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Fruit%20Into%20Baskets%20.md)
* [930. 和相同的二元子数组---Binary Subarrays With Sum](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/930.%20%E5%92%8C%E7%9B%B8%E5%90%8C%E7%9A%84%E4%BA%8C%E5%85%83%E5%AD%90%E6%95%B0%E7%BB%84(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Binary%20Subarrays%20With%20Sum.md)
* [992. K 个不同整数的子数组---Subarrays with K Different Integers ](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/992.%20K%20%E4%B8%AA%E4%B8%8D%E5%90%8C%E6%95%B4%E6%95%B0%E7%9A%84%E5%AD%90%E6%95%B0%E7%BB%84(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Subarrays%20with%20K%20Different%20Integers.md)
* [1004. 最大连续 1 的个数 III---Max Consecutive Ones III](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/1004.%20%E6%9C%80%E5%A4%A7%E8%BF%9E%E7%BB%AD%201%20%E7%9A%84%E4%B8%AA%E6%95%B0%20III(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Max%20Consecutive%20Ones%20III.md)
* [1234. 替换子串得到平衡字符串---Replace the Substring for Balanced String](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/1234.%20%E6%9B%BF%E6%8D%A2%E5%AD%90%E4%B8%B2%E5%BE%97%E5%88%B0%E5%B9%B3%E8%A1%A1%E5%AD%97%E7%AC%A6%E4%B8%B2(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Replace%20the%20Substring%20for%20Balanced%20String.md)
* [1248. 统计「优美子数组」---Count Number of Nice Subarrays](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/1248.%20%E7%BB%9F%E8%AE%A1%E3%80%8C%E4%BC%98%E7%BE%8E%E5%AD%90%E6%95%B0%E7%BB%84%E3%80%8D(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Count%20Number%20of%20Nice%20Subarrays.md)
* [1358 包含所有三种字符的子字符串数目---Number of Substrings Containing All Three Characters](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/LeetCode%E7%AE%97%E6%B3%95%E9%9D%A2%E8%AF%95/1358%20%E5%8C%85%E5%90%AB%E6%89%80%E6%9C%89%E4%B8%89%E7%A7%8D%E5%AD%97%E7%AC%A6%E7%9A%84%E5%AD%90%E5%AD%97%E7%AC%A6%E4%B8%B2%E6%95%B0%E7%9B%AE(%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3)---Number%20of%20Substrings%20Containing%20All%20Three%20Characters.md)


Maximum Sum Subarray of Size K (easy)

Smallest Subarray with a given sum (easy)

Longest Substring with K Distinct Characters (medium)


No-repeat Substring (hard)

Longest Substring with Same Letters after Replacement (hard)

Longest Subarray with Ones after Replacement (hard)
