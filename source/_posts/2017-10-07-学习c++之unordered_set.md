---
layout: content
title: 学习C++之unordered_set
---

## 学习C++之unordered_set
最近在leetcode上做题的时候发现了一些c++的新知识，利用这些新的知识可以更方便的解题，比如unordered_set。我们从leetcode题目出发
# 题目
Given an integer array with even length, where different numbers in this array represent different kinds of candies. Each number means one candy of the corresponding kind. You need to distribute these candies equally in number to brother and sister. Return the maximum number of kinds of candies the sister could gain.

Example 1:
Input: candies = [1,1,2,2,3,3]
Output: 3
Explanation:
There are three different kinds of candies (1, 2 and 3), and two candies for each kind.
Optimal distribution: The sister has candies [1,2,3] and the brother has candies [1,2,3], too. 
The sister has three different kinds of candies. 
Example 2:
Input: candies = [1,1,2,3]
Output: 2
Explanation: For example, the sister has candies [2,3] and the brother has candies [1,1]. 
The sister has two different kinds of candies, the brother has only one kind of candies. 
Note:

The length of the given array is in range [2, 10,000], and will be even.
The number in given array is in range [-100,000, 100,000].

这个题意不是很容易懂，给偶数个糖果，要平均的分给妹妹和弟弟，然后不同的数字表示不同的糖果种类。要求出这样分配种类最多有几种。
# 解题思路
讲道理，我是没什么思路的。。然后看discuss里面的大神给的一些解法，看到了很多使用unordered_set这个类。

# 大佬AC代码
	class Solution {
	public:
		int distributeCandies(vector<int>& candies) {
			unordered_set<int> kinds;
			for(int kind:candies){
				kinds.insert(kind);
			}
			return min(kinds.size(),candies.size()/2);
		}
	};
	
# 分析代码
这个代码真的是很简洁了，主要是unordered_set的使用，在for循环遍历candies的时候，把每一个candy的kind插入kinds。为了弄明白insert是怎么执行的，我在vs里实验了一下。如果是【112233】这样的，插入后，kinds的size是3，相同的数只保存一个因为它是存储唯一（Unique，即无重复）元素的关联容器

# unordered_set
无序集合（Unordered Set）容器是一个存储唯一（Unique，即无重复）元素的关联容器（Associative container），容器中的元素无特别的次序关系。该容器允许基于值地快速元素检索。

## 容器特性：

	关联（Associative）

	关联容器中的元素是通过主键（Key）而不是它们在容器中的绝对位置来引用的。

	无序（Unordered）

	无序容器通过 hash 表来组织它们的元素，允许通过主键快速地访问元素。

	集合（Set）

	元素的值同时可以用来标志对应的元素。

	键唯一（Unique keys）

	容器中不存在两个元素有相同的主键。

	能够感知内存分配器的（Allocator-aware）

	容器使用一个内存分配器对象来动态地处理它的存储需求。
## 详细说明
在一个 unordered_set 容器中，元素的值同时可以用来标志对应的元素（即值是自身的主键），每个值必须是唯一的。主键是不可修改的，因此在 unordered_set 中的元素不能被逐个修改（所有元素保持恒定），但是可以删除某个元素或插入新的元素。

在 unordered_set 内部，元素不会按任何顺序排序，而是通过元素值的 hash 值将元素分组放置到各个槽（Bucket，也可译成“桶”）中，这样就能通过元素值快速地访问各个对应的元素（平均耗时为一个常量，即时间复杂度为 O(1)）。

在访问容器中的某个元素时，unordered_set 容器比 set 容器高效，而在迭代容器元素的某个子集时，前者比后者稍微低效了一点。

unordered_set 容器支持正向迭代。

## 详细介绍以及代码例子
http://classfoo.com/ccby/article/qNNOJ