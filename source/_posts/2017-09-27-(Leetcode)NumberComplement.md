---
layout: content
title: (Leetcode)Number Complement解题记录
---

## (Leetcode)Number Complement解题记录
又是一题位操作的题目，摩拳擦掌表示应该能做出来。。。不过最后确实是写出来了，不过不是最优解


# 题目
Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary representation.

Note:
The given integer is guaranteed to fit within the range of a 32-bit signed integer.
You could assume no leading zero bit in the integer’s binary representation.

Example：
	Input: 5
	Output: 2
	Explanation: The binary representation of 5 is 101 (no leading zero bits), and its complement is 010. So you need to output 2.

题意是输入一个整数，输出一个十进制数，他们的二进制互补

# 解题思路
有了昨天位运算的基础，感觉自己应该能做。首先想到的是先&1，然后再进行移位操作，通过&1是否为0，判断二进制尾位是否为0，然后分情况对输出数字进行移位操作。试了一下发现不可行，比如输入2，二进制是10，互补的应该是01，但是移位出的结果还是10，，，放弃这个想法。
后面的思路就比较暴力了，，直接把二进制数转换为十进制的。。比较蠢的方法，不过ac了
后来在网上看到比较好的解法，是使用mask掩码，使mask^num就可以得到补码！真是很方便，但是我却想不到，完全没想到这种操作，还是太年轻。。

# 算法
比较蠢的方法。。。

	class Solution {
	public:
		int findComplement(int num) {
			int res=0,i=0;
			int ans[32]={0};
			while(num>0){
				if((num&1)==0){
					ans[i++]=1;
				}else
					ans[i++]=0;
				num>>=1;
			}
			
			int len=i;
			for(int x=0;x<len;x++){
				res+=ans[x]*pow(2,x);
			}
			return res;
		}
	};

# 改进
使用mask和num异或操作，这样就能得到补码，mask的获取是使用移位操作。
mask–1为和num二进制位等长的所有位数为1的数（这是一个规律），与num取^可以得到和num相反的数字

	class Solution {
	public:
		int findComplement(int num) {
			int temp = num, mask = 1;
			while(temp){
				temp >>= 1;
				mask <<= 1;
			}
			return ((mask - 1) ^ num);
		}
	};
