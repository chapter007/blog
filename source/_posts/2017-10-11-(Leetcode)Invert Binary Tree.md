---
layout: content
title: (leetcode)Invert Binary Tree
---

## (leetcode)Invert Binary Tree
#一些废话
这题就是传说中那个难倒那个大牛的一题，反转二叉树。其实我看到题也不会，慢慢积累吧。
# 题目
Invert a binary tree.

     4
   /   \
  2     7
 / \   / \
1   3 6   9
to
     4
   /   \
  7     2
 / \   / \
9   6 3   1

	Google: 90% of our engineers use the software you wrote (Homebrew), but you can’t invert a binary tree on a whiteboard so fuck off.
题意通过例子很容易懂，就是交换二叉树的左右节点，这题有递归和非递归两种方法，都不难实现
# AC代码
递归版本：
	class Solution {
	public:
		TreeNode* invertTree(TreeNode* root) {
			if(root){
				invertTree(root->left);
				invertTree(root->right);
				swap(root->left,root->right);
			}
			return root;
		}
	};

非递归版本：
	class Solution {
	public:
		TreeNode* invertTree(TreeNode* root) {
			stack<TreeNode*> s;
			s.push(root);
			while(!s.empty()){
				TreeNode* p=s.top();
				s.pop();
				if(p){
					s.push(p->left);
					s.push(p->right);
					swap(p->left,p->right);
				}
			}
			return root;
		}
	};
	
递归版本的代码更加简洁，但是不是很容易理解，emmm一层层的循环嵌套让我有点晕。非递归的版本使用了栈，就是树的遍历，在遍历的过程中交换了左右节点。

# 关于以后的一些想法
其实在考研结束以后，我就开始纠结这个问题了。以后是做安卓开发还是web开发，还是学习大数据，数据挖掘这类？想了很久，直到今天。看了一些博客，一些论坛上的讨论，有点想法了。
* 不管以后想做什么，算法始终是基础，基础就是牢固了学别的都很快。算法不仅是基础，也是面试必考的内容！所以学习算法是首要任务
* 除了算法以外，操作系统，计算机网络，数据库也是基础，这些知识也需要牢固！
* 关于是学习安卓还是web，或是大数据，我都可以接触一下，其实安卓和web以前已经有一定的基础了。
