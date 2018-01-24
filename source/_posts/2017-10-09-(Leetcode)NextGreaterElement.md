---
layout: content
title: (leetcode)496. Next Greater Element I
---

## (leetcode)496. Next Greater Element I
# 题目
You are given two arrays (without duplicates) nums1 and nums2 where nums1’s elements are subset of nums2. Find all the next greater numbers for nums1's elements in the corresponding places of nums2.

The Next Greater Number of a number x in nums1 is the first greater number to its right in nums2. If it does not exist, output -1 for this number.

Example 1:
Input: nums1 = [4,1,2], nums2 = [1,3,4,2].
Output: [-1,3,-1]
Explanation:
    For number 4 in the first array, you cannot find the next greater number for it in the second array, so output -1.
    For number 1 in the first array, the next greater number for it in the second array is 3.
    For number 2 in the first array, there is no next greater number for it in the second array, so output -1.
Example 2:
Input: nums1 = [2,4], nums2 = [1,2,3,4].
Output: [3,-1]
Explanation:
    For number 2 in the first array, the next greater number for it in the second array is 3.
    For number 4 in the first array, there is no next greater number for it in the second array, so output -1.
Note:
All elements in nums1 and nums2 are unique.
The length of both nums1 and nums2 would not exceed 1000.
这题下午在看的时候感觉能做，晚上回来就被打脸了。。。我能想到的解法自然是比较基础的遍历两个数组，从第一个数组中拿一个数到第二个数组中做比较，先是找到这个数字，然后看这个数字后面有没有比它更大的数字，如果有，就放到结果集里，如果没有，就放-1到结果集中。
事实上，两层嵌套的遍历会带来很多问题。
我的天那。。。东拼西凑凑出来了。。。今晚不想写了，明天在看大佬的解法吧

# AC代码
	class Solution {
	public:
		vector<int> nextGreaterElement(vector<int>& findNums, vector<int>& nums) {
			vector<int> res;
			
			for(int i=0;i<findNums.size();i++){
				bool flag=false;
				for(int j=0;j<nums.size();j++){
					if(findNums[i]==nums[j]){
						for(int x=j;x<nums.size();x++){
							if(findNums[i]<nums[x+1]&&x+1<nums.size()){
								res.push_back(nums[x+1]);
								flag=true;
								break;
							}
						}
						if(flag==false) res.push_back(-1);
					}
				}
			}
			return res;
		}
	};
方法和我上面说的一样，实现起来比较麻烦，嵌套了好几层for循环，效率很低，虽然强行ac了

# 大神的代码
	class Solution {
	public:
		vector<int> nextGreaterElement(vector<int>& findNums, vector<int>& nums) {
			stack<int> s;
			unordered_map<int, int> m;
			for (int n : nums) {
				while (s.size() && s.top() < n) {
					m[s.top()] = n;
					s.pop();
				}
				s.push(n);
			}
			vector<int> ans;
			for (int n : findNums) ans.push_back(m.count(n) ? m[n] : -1);
			return ans;
		}
	};
	
可见使用了stack和unordered_map这两个数据类型（虽然前面已经做过不少几次这些数据类型的题了，但是我还是难以主动使用）
map 用来存放nums里面的数字，stack起到了一个中间商的作用
在while循环中，把符合条件的数字存储到了map里面。当第一个for循环结束的时候，就已经把nums里的数字归好类了。因为findnums是nums的子集，再遍历一次findnums就可以轻松的写出答案。
关键点是第一个for循环，其实按照题目规则，比如【1，3，4，2】这个序列，只有1有Greater num，是3。。
## 解释的不是很明白，这个做法很难想到啊