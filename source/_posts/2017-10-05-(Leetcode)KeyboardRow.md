---
layout: content
title: (Leetcode)Keyboard Row解题记录
---

## (Leetcode)Keyboard Row解题记录
这是一题字符串有关的题目，我只想到了笨方法，而且实现起来比较复杂，感觉写出来需要很久
# 题目
Given a List of words, return the words that can be typed using letters of alphabet on only one row's of American keyboard like the image below.

Example 1:

Input: ["Hello", "Alaska", "Dad", "Peace"]
Output: ["Alaska", "Dad"]
 

Note:

You may use one character in the keyboard more than once.
You may assume the input string will only contain letters of alphabet.

题意是输入一些单词，返回那些字母全在键盘上同一行的单词，比较好懂
# 解题思路
思路很清晰，键盘上每一行的字母都是确定的，把每一行都存储到数组里面，然后遍历单词，就可以知道单词的字母在哪一行了，如果所有字母不在同一行则不符合规则。
事实上这样的效率会比较低，需要遍历单词，还需要遍历每一行的字母，嵌套遍历了。后来在网上看到别的解法，思路相似，但是使用unordered_set count可以快速得知单词里的字母是否在某一行中。需要补充一些c++的语法知识了。

## 补充知识
### vector
vector(向量): C++中的一种数据结构,确切的说是一个类.它相当于一个动态的数组,当程序员无法知道自己需要的数组的规模多大时,用其来解决问题可以达到最大节约空间的目的.
用法:

1.文件包含:     
	首先在程序开头处加上#include<vector>以包含所需要的类文件vector还有一定要加上using namespace std;
2.变量声明:
	2.1 例:声明一个int向量以替代一维的数组:vector <int> a;(等于声明了一个int数组a[],大小没有指定,可以动态的向里面添加删除)。
	2.2 例:用vector代替二维数组.其实只要声明一个一维数组向量即可,而一个数组的名字其实代表的是它的首地址,所以只要声明一个地址的向量即可,即:vector <int *> a.同理想用向量代替三维数组也是一样,vector <int**>a;再往上面依此类推.

3.具体的用法以及函数调用:

	3.1 如何得到向量中的元素?其用法和数组一样:
	例如:
        vector <int *> a
        int b = 5;
        a.push_back(b);//该函数下面有详解
        cout<<a[0];       //输出结果为5

			push_back   在数组的最后添加一个数据
			pop_back    去掉数组的最后一个数据 
			at                得到编号位置的数据
			begin           得到数组头的指针
			end             得到数组的最后一个单元+1的指针
			front        得到数组头的引用
			back            得到数组的最后一个单元的引用
			max_size     得到vector最大可以是多大
			capacity       当前vector分配的大小
			size           当前使用数据的大小
			resize         改变当前使用数据的大小，如果它比当前使用的大，者填充默认值
			reserve      改变当前vecotr所分配空间的大小
			erase         删除指针指向的数据项
			clear          清空当前的vector
			rbegin        将vector反转后的开始指针返回(其实就是原来的end-1)
			rend          将vector反转构的结束指针返回(其实就是原来的begin-1)
			empty        判断vector是否为空
			swap         与另一个vector交换数据

         3.2  详细的函数实现功能：其中vector<int> c.
				c.clear()         移除容器中所有数据。
				c.empty()         判断容器是否为空。
				c.erase(pos)        删除pos位置的数据
				c.erase(beg,end) 删除[beg,end)区间的数据
				c.front()         传回第一个数据。
				c.insert(pos,elem)  在pos位置插入一个elem拷贝
				c.pop_back()     删除最后一个数据。
				c.push_back(elem) 在尾部加入一个数据。
				c.resize(num)     重新设置该容器的大小
				c.size()         回容器中实际数据的个数。
				c.begin()           返回指向容器第一个元素的迭代器
				c.end()             返回指向容器最后一个元素的迭代器
### unordered_set
C++11中出现了两种新的关联容器:unordered_set和unordered_map，其内部实现与set和map大有不同，set和map内部实现是基于RB-Tree，而unordered_set和unordered_map内部实现是基于哈希表(hashtable)，由于unordered_set和unordered_map内部实现的公共接口大致相同，所以本文以unordered_set为例。
unordered_set是基于哈希表，因此要了解unordered_set，就必须了解哈希表的机制。
哈希表是根据关键码值而进行直接访问的数据结构，通过相应的哈希函数(也称散列函数)处理关键字得到相应的关键码值，关键码值对应着一个特定位置，用该位置来存取相应的信息，这样就能以较快的速度获取关键字的信息。
比如：现有公司员工的个人信息（包括年龄），需要查询某个年龄的员工个数。由于人的年龄范围大约在[0，200]，所以可以开一个200大小的数组，然后通过哈希函数得到key对应的key-value，这样就能完成统计某个年龄的员工个数。
而在这个例子中，也存在这样一个问题，两个员工的年龄相同，但其他信息（如：名字、身份证）不同，通过前面说的哈希函数，会发现其都位于数组的相同位置，这里，就涉及到“冲突”。
准确来说，冲突是不可避免的，而解决冲突的方法常见的有：开发地址法、再散列法、链地址法(也称拉链法)。而unordered_set内部解决冲突采用的是----链地址法，当用冲突发生时把具有同一关键码的数据组成一个链表。

### 它的count方法
if an element with a value equivalent to k is found, or zero otherwise.如果一个元素的值和k是相等的，就返回1，否则返回0.
# AC代码
	class Solution {
	public:
		vector<string> findWords(vector<string>& words) {
		    unordered_set<char> row1 {'q', 'w', 'e', 'r', 't', 'y','u', 'i', 'o', 'p'};
			unordered_set<char> row2 {'a', 's', 'd', 'f', 'g', 'h', 'j', 'k', 'l'}; 
			unordered_set<char> row3 { 'z', 'x', 'c', 'v', 'b' ,'n', 'm'};
			//使用unordered_set存储每一行的字母
			
			vector<unordered_set<char>> rows {row1, row2, row3};
			//再把哈希表放到vector里
			
			vector<string> validWords;
			for(int i=0; i<words.size(); ++i){
				//遍历单词
				int row=0;
				
				for(int k=0; k<3; ++k){
					if(rows[k].count((char)tolower(words[i][0])) > 0) row = k;
					//tolower函数可以把大写字母转换成小写
				}
				
				validWords.push_back(words[i]);
				//把单词放到validwords里面
				for(int j=1; j<words[i].size(); ++j){
				
					if(rows[row].count((char)tolower(words[i][j])) == 0){
						validWords.pop_back();//不符合要求的单词弹出
						break;
					}
				}
				
			}
			return validWords;
		}
	};
	
### AC代码理解
这段代码主要需要理解的就是三个循环，第一个大循环是遍历单词，第二个循环是遍历rows，找到单词的第一个字母所在行，并且记录下行号，第三个循环是遍历单词的每一个字母，第一个字母所在行已经确定了，后面的也必须在这一行，否则不合格，弹出这个单词

# 优化解法
	class Solution {
	public:
	vector<string> findWords(vector<string>& words) 
	{
		vector<string> res;
		
		for(auto str : words)
		{
			bool r1 = str.find_first_of("QWERTYUIOPqwertyuiop") == string::npos ? false : true;
			bool r2 = str.find_first_of("ASDFGHJKLasdfghjkl") == string::npos ? false : true;
			bool r3 = str.find_first_of("ZXCVBNMzxcvbnm") == string::npos ? false : true;
			
			if(r1 + r2 + r3 == 1)
				res.push_back(str);
		}
		
		return res;
	}
		
	};

## 关于优化解法
优化解法看上去都是很简洁啊，膜拜大佬。这个只需要一个循环，遍历单词，str是每一个单词，而对于find_first_of这个方法，我也是不知道。。。查了一波

其实这个也比较好理解，就是每个单词查找它是否在某一行。。。不是很理解str.find_first_of("QWERTYUIOPqwertyuiop")是怎么运行的准备试验一下，emmmm，懂了！
bool r1 = str.find_first_of("QWERTYUIOPqwertyuiop") == string::npos ? false : true;
bool r2 = str.find_first_of("ASDFGHJKLasdfghjkl") == string::npos ? false : true;
bool r3 = str.find_first_of("ZXCVBNMzxcvbnm") == string::npos ? false : true;
这三行是核心，用str，也就是每个单词，去寻找它里面的字母是否在这三行里，只有全在一行里，才能使r1 + r2 + r3 == 1
所以判断成功

以下是查找的资料：
string 类提供字符串处理函数，利用这些函数，程序员可以在字符串内查找字符，
提取连续字符序列(称为子串)，以及在字符串中删除和添加。我们将介绍一些主要函数。

1.函数find_first_of()和 find_last_of() 执行简单的模式匹配
例如：在字符串中查找单个字符c。
函数find_first_of() 查找在字符串中第1个出现的字符c，而函数find_last_of()查找最后
一个出现的c。匹配的位置是返回值。如果没有匹配发生，则函数返回-1.
   
          int find_first_of(char c, int start = 0):
              查找字符串中第1个出现的c,由位置start开始。
              如果有匹配，则返回匹配位置；否则，返回-1.默认情况下，start为0，函数搜索
              整个字符串。
              
          int find_last_of(char c):
              查找字符串中最后一个出现的c。有匹配，则返回匹配位置；否则返回-1.
              该搜索在字符末尾查找匹配，所以没有提供起始位置。
string::npos好像就是-1？static const size_t npos = -1;  