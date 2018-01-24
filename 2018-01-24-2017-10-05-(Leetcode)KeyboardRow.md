<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  

  
  <title>(Leetcode)Keyboard Row解题记录 | 张杰的日志</title>
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
  <meta name="description" content="(Leetcode)Keyboard Row解题记录这是一题字符串有关的题目，我只想到了笨方法，而且实现起来比较复杂，感觉写出来需要很久 题目Given a List of words, return the words that can be typed using letters of alphabet on only one row’s of American keyboard like t">
<meta property="og:type" content="article">
<meta property="og:title" content="(Leetcode)Keyboard Row解题记录">
<meta property="og:url" content="http://yoursite.com/2018-01-24-2017-10-05-(Leetcode)KeyboardRow.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="(Leetcode)Keyboard Row解题记录这是一题字符串有关的题目，我只想到了笨方法，而且实现起来比较复杂，感觉写出来需要很久 题目Given a List of words, return the words that can be typed using letters of alphabet on only one row’s of American keyboard like t">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2017-10-06T02:47:32.078Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(Leetcode)Keyboard Row解题记录">
<meta name="twitter:description" content="(Leetcode)Keyboard Row解题记录这是一题字符串有关的题目，我只想到了笨方法，而且实现起来比较复杂，感觉写出来需要很久 题目Given a List of words, return the words that can be typed using letters of alphabet on only one row’s of American keyboard like t">
  
    <link rel="alternate" href="/atom.xml" title="张杰的日志" type="application/atom+xml">
  
  
    <link rel="icon" href="/favicon.png">
  
  
    <link href="//fonts.googleapis.com/css?family=Source+Code+Pro" rel="stylesheet" type="text/css">
  
  <link rel="stylesheet" href="/css/style.css">
</head>

<body>
  <div id="container">
    <div id="wrap">
      <header id="header">
  <div id="banner"></div>
  <div id="header-outer" class="outer">
    <div id="header-title" class="inner">
      <h1 id="logo-wrap">
        <a href="/" id="logo">张杰的日志</a>
      </h1>
      
        <h2 id="subtitle-wrap">
          <a href="/" id="subtitle">记录学习生活</a>
        </h2>
      
    </div>
    <div id="header-inner" class="inner">
      <nav id="main-nav">
        <a id="main-nav-toggle" class="nav-icon"></a>
        
          <a class="main-nav-link" href="/">Home</a>
        
          <a class="main-nav-link" href="/archives">Archives</a>
        
      </nav>
      <nav id="sub-nav">
        
          <a id="nav-rss-link" class="nav-icon" href="/atom.xml" title="RSS Feed"></a>
        
        <a id="nav-search-btn" class="nav-icon" title="Suche"></a>
      </nav>
      <div id="search-form-wrap">
        <form action="//google.com/search" method="get" accept-charset="UTF-8" class="search-form"><input type="search" name="q" class="search-form-input" placeholder="Search"><button type="submit" class="search-form-submit">&#xF002;</button><input type="hidden" name="sitesearch" value="http://yoursite.com"></form>
      </div>
    </div>
  </div>
</header>
      <div class="outer">
        <section id="main"><article id="content-2017-10-05-(Leetcode)KeyboardRow" class="article article-type-content" itemscope itemprop="blogPost">
  <div class="article-meta">
    <a href="/2018-01-24-2017-10-05-(Leetcode)KeyboardRow.md" class="article-date">
  <time datetime="2018-01-24T13:16:48.333Z" itemprop="datePublished">2018-01-24</time>
</a>
    
  </div>
  <div class="article-inner">
    
    
      <header class="article-header">
        
  
    <h1 class="article-title" itemprop="name">
      (Leetcode)Keyboard Row解题记录
    </h1>
  

      </header>
    
    <div class="article-entry" itemprop="articleBody">
      
        <h2 id="Leetcode-Keyboard-Row解题记录"><a href="#Leetcode-Keyboard-Row解题记录" class="headerlink" title="(Leetcode)Keyboard Row解题记录"></a>(Leetcode)Keyboard Row解题记录</h2><p>这是一题字符串有关的题目，我只想到了笨方法，而且实现起来比较复杂，感觉写出来需要很久</p>
<h1 id="题目"><a href="#题目" class="headerlink" title="题目"></a>题目</h1><p>Given a List of words, return the words that can be typed using letters of alphabet on only one row’s of American keyboard like the image below.</p>
<p>Example 1:</p>
<p>Input: [“Hello”, “Alaska”, “Dad”, “Peace”]<br>Output: [“Alaska”, “Dad”]</p>
<p>Note:</p>
<p>You may use one character in the keyboard more than once.<br>You may assume the input string will only contain letters of alphabet.</p>
<p>题意是输入一些单词，返回那些字母全在键盘上同一行的单词，比较好懂</p>
<h1 id="解题思路"><a href="#解题思路" class="headerlink" title="解题思路"></a>解题思路</h1><p>思路很清晰，键盘上每一行的字母都是确定的，把每一行都存储到数组里面，然后遍历单词，就可以知道单词的字母在哪一行了，如果所有字母不在同一行则不符合规则。<br>事实上这样的效率会比较低，需要遍历单词，还需要遍历每一行的字母，嵌套遍历了。后来在网上看到别的解法，思路相似，但是使用unordered_set count可以快速得知单词里的字母是否在某一行中。需要补充一些c++的语法知识了。</p>
<h2 id="补充知识"><a href="#补充知识" class="headerlink" title="补充知识"></a>补充知识</h2><h3 id="vector"><a href="#vector" class="headerlink" title="vector"></a>vector</h3><p>vector(向量): C++中的一种数据结构,确切的说是一个类.它相当于一个动态的数组,当程序员无法知道自己需要的数组的规模多大时,用其来解决问题可以达到最大节约空间的目的.<br>用法:</p>
<p>1.文件包含:<br>    首先在程序开头处加上#include<vector>以包含所需要的类文件vector还有一定要加上using namespace std;<br>2.变量声明:<br>    2.1 例:声明一个int向量以替代一维的数组:vector <int> a;(等于声明了一个int数组a[],大小没有指定,可以动态的向里面添加删除)。<br>    2.2 例:用vector代替二维数组.其实只要声明一个一维数组向量即可,而一个数组的名字其实代表的是它的首地址,所以只要声明一个地址的向量即可,即:vector <int *=""> a.同理想用向量代替三维数组也是一样,vector <int**>a;再往上面依此类推.</int**></int></int></vector></p>
<p>3.具体的用法以及函数调用:</p>
<pre><code>3.1 如何得到向量中的元素?其用法和数组一样:
例如:
    vector &lt;int *&gt; a
    int b = 5;
    a.push_back(b);//该函数下面有详解
    cout&lt;&lt;a[0];       //输出结果为5

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

     3.2  详细的函数实现功能：其中vector&lt;int&gt; c.
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
</code></pre><h3 id="unordered-set"><a href="#unordered-set" class="headerlink" title="unordered_set"></a>unordered_set</h3><p>C++11中出现了两种新的关联容器:unordered_set和unordered_map，其内部实现与set和map大有不同，set和map内部实现是基于RB-Tree，而unordered_set和unordered_map内部实现是基于哈希表(hashtable)，由于unordered_set和unordered_map内部实现的公共接口大致相同，所以本文以unordered_set为例。<br>unordered_set是基于哈希表，因此要了解unordered_set，就必须了解哈希表的机制。<br>哈希表是根据关键码值而进行直接访问的数据结构，通过相应的哈希函数(也称散列函数)处理关键字得到相应的关键码值，关键码值对应着一个特定位置，用该位置来存取相应的信息，这样就能以较快的速度获取关键字的信息。<br>比如：现有公司员工的个人信息（包括年龄），需要查询某个年龄的员工个数。由于人的年龄范围大约在[0，200]，所以可以开一个200大小的数组，然后通过哈希函数得到key对应的key-value，这样就能完成统计某个年龄的员工个数。<br>而在这个例子中，也存在这样一个问题，两个员工的年龄相同，但其他信息（如：名字、身份证）不同，通过前面说的哈希函数，会发现其都位于数组的相同位置，这里，就涉及到“冲突”。<br>准确来说，冲突是不可避免的，而解决冲突的方法常见的有：开发地址法、再散列法、链地址法(也称拉链法)。而unordered_set内部解决冲突采用的是—-链地址法，当用冲突发生时把具有同一关键码的数据组成一个链表。</p>
<h3 id="它的count方法"><a href="#它的count方法" class="headerlink" title="它的count方法"></a>它的count方法</h3><p>if an element with a value equivalent to k is found, or zero otherwise.如果一个元素的值和k是相等的，就返回1，否则返回0.</p>
<h1 id="AC代码"><a href="#AC代码" class="headerlink" title="AC代码"></a>AC代码</h1><pre><code>class Solution {
public:
    vector&lt;string&gt; findWords(vector&lt;string&gt;&amp; words) {
        unordered_set&lt;char&gt; row1 {&apos;q&apos;, &apos;w&apos;, &apos;e&apos;, &apos;r&apos;, &apos;t&apos;, &apos;y&apos;,&apos;u&apos;, &apos;i&apos;, &apos;o&apos;, &apos;p&apos;};
        unordered_set&lt;char&gt; row2 {&apos;a&apos;, &apos;s&apos;, &apos;d&apos;, &apos;f&apos;, &apos;g&apos;, &apos;h&apos;, &apos;j&apos;, &apos;k&apos;, &apos;l&apos;}; 
        unordered_set&lt;char&gt; row3 { &apos;z&apos;, &apos;x&apos;, &apos;c&apos;, &apos;v&apos;, &apos;b&apos; ,&apos;n&apos;, &apos;m&apos;};
        //使用unordered_set存储每一行的字母

        vector&lt;unordered_set&lt;char&gt;&gt; rows {row1, row2, row3};
        //再把哈希表放到vector里

        vector&lt;string&gt; validWords;
        for(int i=0; i&lt;words.size(); ++i){
            //遍历单词
            int row=0;

            for(int k=0; k&lt;3; ++k){
                if(rows[k].count((char)tolower(words[i][0])) &gt; 0) row = k;
                //tolower函数可以把大写字母转换成小写
            }

            validWords.push_back(words[i]);
            //把单词放到validwords里面
            for(int j=1; j&lt;words[i].size(); ++j){

                if(rows[row].count((char)tolower(words[i][j])) == 0){
                    validWords.pop_back();//不符合要求的单词弹出
                    break;
                }
            }

        }
        return validWords;
    }
};
</code></pre><h3 id="AC代码理解"><a href="#AC代码理解" class="headerlink" title="AC代码理解"></a>AC代码理解</h3><p>这段代码主要需要理解的就是三个循环，第一个大循环是遍历单词，第二个循环是遍历rows，找到单词的第一个字母所在行，并且记录下行号，第三个循环是遍历单词的每一个字母，第一个字母所在行已经确定了，后面的也必须在这一行，否则不合格，弹出这个单词</p>
<h1 id="优化解法"><a href="#优化解法" class="headerlink" title="优化解法"></a>优化解法</h1><pre><code>class Solution {
public:
vector&lt;string&gt; findWords(vector&lt;string&gt;&amp; words) 
{
    vector&lt;string&gt; res;

    for(auto str : words)
    {
        bool r1 = str.find_first_of(&quot;QWERTYUIOPqwertyuiop&quot;) == string::npos ? false : true;
        bool r2 = str.find_first_of(&quot;ASDFGHJKLasdfghjkl&quot;) == string::npos ? false : true;
        bool r3 = str.find_first_of(&quot;ZXCVBNMzxcvbnm&quot;) == string::npos ? false : true;

        if(r1 + r2 + r3 == 1)
            res.push_back(str);
    }

    return res;
}

};
</code></pre><h2 id="关于优化解法"><a href="#关于优化解法" class="headerlink" title="关于优化解法"></a>关于优化解法</h2><p>优化解法看上去都是很简洁啊，膜拜大佬。这个只需要一个循环，遍历单词，str是每一个单词，而对于find_first_of这个方法，我也是不知道。。。查了一波</p>
<p>其实这个也比较好理解，就是每个单词查找它是否在某一行。。。不是很理解str.find_first_of(“QWERTYUIOPqwertyuiop”)是怎么运行的准备试验一下，emmmm，懂了！<br>bool r1 = str.find_first_of(“QWERTYUIOPqwertyuiop”) == string::npos ? false : true;<br>bool r2 = str.find_first_of(“ASDFGHJKLasdfghjkl”) == string::npos ? false : true;<br>bool r3 = str.find_first_of(“ZXCVBNMzxcvbnm”) == string::npos ? false : true;<br>这三行是核心，用str，也就是每个单词，去寻找它里面的字母是否在这三行里，只有全在一行里，才能使r1 + r2 + r3 == 1<br>所以判断成功</p>
<p>以下是查找的资料：<br>string 类提供字符串处理函数，利用这些函数，程序员可以在字符串内查找字符，<br>提取连续字符序列(称为子串)，以及在字符串中删除和添加。我们将介绍一些主要函数。</p>
<p>1.函数find_first_of()和 find_last_of() 执行简单的模式匹配<br>例如：在字符串中查找单个字符c。<br>函数find_first_of() 查找在字符串中第1个出现的字符c，而函数find_last_of()查找最后<br>一个出现的c。匹配的位置是返回值。如果没有匹配发生，则函数返回-1.</p>
<pre><code>int find_first_of(char c, int start = 0):
    查找字符串中第1个出现的c,由位置start开始。
    如果有匹配，则返回匹配位置；否则，返回-1.默认情况下，start为0，函数搜索
    整个字符串。

int find_last_of(char c):
    查找字符串中最后一个出现的c。有匹配，则返回匹配位置；否则返回-1.
    该搜索在字符末尾查找匹配，所以没有提供起始位置。
</code></pre><p>string::npos好像就是-1？static const size_t npos = -1;  </p>

      
    </div>
    <footer class="article-footer">
      <a data-url="http://yoursite.com/2018-01-24-2017-10-05-(Leetcode)KeyboardRow.md" data-id="cjct4js45000c28u7x7t35dxh" class="article-share-link">Teilen</a>
      
      
    </footer>
  </div>
  
    
<nav id="article-nav">
  
    <a href="/2018-01-24-2017-10-07-学习c++之unordered_set.md" id="article-nav-newer" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Neuer</strong>
      <div class="article-nav-title">
        
          学习C++之unordered_set
        
      </div>
    </a>
  
  
    <a href="/2018-01-24-2017-10-04-学习java之iterable.md" id="article-nav-older" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Älter</strong>
      <div class="article-nav-title">学习java之iterable</div>
    </a>
  
</nav>

  
</article>

</section>
        
          <aside id="sidebar">
  
    

  
    

  
    
  
    
  <div class="widget-wrap">
    <h3 class="widget-title">Archiv</h3>
    <div class="widget">
      <ul class="archive-list"><li class="archive-list-item"><a class="archive-list-link" href="/archives/2018/01/">January 2018</a></li></ul>
    </div>
  </div>


  
    
  <div class="widget-wrap">
    <h3 class="widget-title">letzter Beitrag</h3>
    <div class="widget">
      <ul>
        
          <li>
            <a href="/2018-01-24-2017-10-22-写写日记.md">дд�ռ�</a>
          </li>
        
          <li>
            <a href="/2018-01-24-2017-10-12-学习android之四大核心组件.md">学习android之四大组件</a>
          </li>
        
          <li>
            <a href="/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md">(leetcode)Invert Binary Tree</a>
          </li>
        
          <li>
            <a href="/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md">(leetcode)496. Next Greater Element I</a>
          </li>
        
          <li>
            <a href="/2018-01-24-2017-10-07-学习c++之unordered_set.md">学习C++之unordered_set</a>
          </li>
        
      </ul>
    </div>
  </div>

  
</aside>
        
      </div>
      <footer id="footer">
  
  <div class="outer">
    <div id="footer-info" class="inner">
      &copy; 2018 zhangjie<br>
      Powered by <a href="http://hexo.io/" target="_blank">Hexo</a>
    </div>
  </div>
</footer>
    </div>
    <nav id="mobile-nav">
  
    <a href="/" class="mobile-nav-link">Home</a>
  
    <a href="/archives" class="mobile-nav-link">Archives</a>
  
</nav>
    

<script src="//ajax.googleapis.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>


  <link rel="stylesheet" href="/fancybox/jquery.fancybox.css">
  <script src="/fancybox/jquery.fancybox.pack.js"></script>


<script src="/js/script.js"></script>



  </div>
</body>
</html>