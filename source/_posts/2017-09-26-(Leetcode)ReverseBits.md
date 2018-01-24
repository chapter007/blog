---
layout: content
title: (Leetcode)ReverseBits解题记录
---

# 继续Leetcode
感觉看书上的代码效率并不高，还是写Leetcode比较好


# 题目
Reverse bits of a given 32 bits unsigned integer.

For example, given input 43261596 (represented in binary as 00000010100101000001111010011100), return 964176192 (represented in binary as 00111001011110000010100101000000).

Follow up:
If this function is called many times, how would you optimize it?

Related problem: Reverse Integer

题意是给定一个32位无符号的整数，然后反转这个数的二进制形式，得到一个新的32位无符号整数，注意这是十进制的

# 解题思路
有了前面的Hamming Distance基础，可以联想到这题应该也是用位运算。不过，我只想到了把无符号整数&1，可以快速得到2进制的数，但是我那样还要转换回十进制。。。做了一会，还是跪了。在网上找到别的方法，使用位运算的左右移位操作即可实现这个要求。
当给定的数字n,最后一位n&1==1，则把要输出的数 m>>1+1,如果n&1==0，则m>>1,这个操作是在一个32次循环中
因为32位数字，每次操作后n需要右移一位n<<=1

# 算法

	class Solution {
	public:
		uint32_t reverseBits(uint32_t n) {
			uint32_t m=0;
			for(int i=0;i<32;i++){
				if((n&1)==1){
					m=(m<<1)+1;
					n>>=1;
				}else{
					m=m<<1;
					n>>=1;
				}
			}
			return m;
		}
	};

# 改进
在Leetcode的discuss里看到的o(1)解法，给跪了。。。不过我倒是没看懂

	class Solution {
	public:
		uint32_t reverseBits(uint32_t n) {
			n = (n >> 16) | (n << 16);
			n = ((n & 0xff00ff00) >> 8) | ((n & 0x00ff00ff) << 8);
			n = ((n & 0xf0f0f0f0) >> 4) | ((n & 0x0f0f0f0f) << 4);
			n = ((n & 0xcccccccc) >> 2) | ((n & 0x33333333) << 2);
			n = ((n & 0xaaaaaaaa) >> 1) | ((n & 0x55555555) << 1);
			return n;
		}
	};
