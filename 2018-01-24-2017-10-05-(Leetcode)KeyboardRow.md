<!DOCTYPE html>



  


<html class="theme-next gemini use-motion" lang="zh-Hans">
<head>
  <meta charset="UTF-8"/>
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1"/>
<meta name="theme-color" content="#222">









<meta http-equiv="Cache-Control" content="no-transform" />
<meta http-equiv="Cache-Control" content="no-siteapp" />
















  
  
  <link href="/blog/lib/fancybox/source/jquery.fancybox.css?v=2.1.5" rel="stylesheet" type="text/css" />







<link href="/blog/lib/font-awesome/css/font-awesome.min.css?v=4.6.2" rel="stylesheet" type="text/css" />

<link href="/blog/css/main.css?v=5.1.4" rel="stylesheet" type="text/css" />


  <link rel="apple-touch-icon" sizes="180x180" href="/blog/images/apple-touch-icon-next.png?v=5.1.4">


  <link rel="icon" type="image/png" sizes="32x32" href="/blog/images/favicon-32x32-next.png?v=5.1.4">


  <link rel="icon" type="image/png" sizes="16x16" href="/blog/images/favicon-16x16-next.png?v=5.1.4">


  <link rel="mask-icon" href="/blog/images/logo.svg?v=5.1.4" color="#222">





  <meta name="keywords" content="Hexo, NexT" />










<meta name="description" content="(Leetcode)Keyboard Row解题记录这是一题字符串有关的题目，我只想到了笨方法，而且实现起来比较复杂，感觉写出来需要很久 题目Given a List of words, return the words that can be typed using letters of alphabet on only one row&amp;apos;s of American keyboard l">
<meta property="og:type" content="article">
<meta property="og:title" content="(Leetcode)Keyboard Row解题记录">
<meta property="og:url" content="http://chapter007.github.io/blog/2018-01-24-2017-10-05-(Leetcode)KeyboardRow.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="(Leetcode)Keyboard Row解题记录这是一题字符串有关的题目，我只想到了笨方法，而且实现起来比较复杂，感觉写出来需要很久 题目Given a List of words, return the words that can be typed using letters of alphabet on only one row&amp;apos;s of American keyboard l">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2018-01-25T01:00:22.572Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(Leetcode)Keyboard Row解题记录">
<meta name="twitter:description" content="(Leetcode)Keyboard Row解题记录这是一题字符串有关的题目，我只想到了笨方法，而且实现起来比较复杂，感觉写出来需要很久 题目Given a List of words, return the words that can be typed using letters of alphabet on only one row&amp;apos;s of American keyboard l">



<script type="text/javascript" id="hexo.configurations">
  var NexT = window.NexT || {};
  var CONFIG = {
    root: '/blog/',
    scheme: 'Gemini',
    version: '5.1.4',
    sidebar: {"position":"left","display":"post","offset":12,"b2t":false,"scrollpercent":false,"onmobile":false},
    fancybox: true,
    tabs: true,
    motion: {"enable":true,"async":false,"transition":{"post_block":"fadeIn","post_header":"slideDownIn","post_body":"slideDownIn","coll_header":"slideLeftIn","sidebar":"slideUpIn"}},
    duoshuo: {
      userId: '0',
      author: '博主'
    },
    algolia: {
      applicationID: '',
      apiKey: '',
      indexName: '',
      hits: {"per_page":10},
      labels: {"input_placeholder":"Search for Posts","hits_empty":"We didn't find any results for the search: ${query}","hits_stats":"${hits} results found in ${time} ms"}
    }
  };
</script>



  <link rel="canonical" href="http://chapter007.github.io/blog/2018-01-24-2017-10-05-(Leetcode)KeyboardRow.md"/>





  <title>(Leetcode)Keyboard Row解题记录 | 张杰的日志</title>
  








</head>

<body itemscope itemtype="http://schema.org/WebPage" lang="zh-Hans">

  
  
    
  

  <div class="container sidebar-position-left page-post-detail">
    <div class="headband"></div>

    <header id="header" class="header" itemscope itemtype="http://schema.org/WPHeader">
      <div class="header-inner"><div class="site-brand-wrapper">
  <div class="site-meta ">
    

    <div class="custom-logo-site-title">
      <a href="/blog/"  class="brand" rel="start">
        <span class="logo-line-before"><i></i></span>
        <span class="site-title">张杰的日志</span>
        <span class="logo-line-after"><i></i></span>
      </a>
    </div>
      
        <p class="site-subtitle">记录学习生活</p>
      
  </div>

  <div class="site-nav-toggle">
    <button>
      <span class="btn-bar"></span>
      <span class="btn-bar"></span>
      <span class="btn-bar"></span>
    </button>
  </div>
</div>

<nav class="site-nav">
  

  
    <ul id="menu" class="menu">
      
        
        <li class="menu-item menu-item-home">
          <a href="/blog/" rel="section">
            
              <i class="menu-item-icon fa fa-fw fa-home"></i> <br />
            
            首页
          </a>
        </li>
      
        
        <li class="menu-item menu-item-archives">
          <a href="/blog/archives/" rel="section">
            
              <i class="menu-item-icon fa fa-fw fa-archive"></i> <br />
            
            归档
          </a>
        </li>
      

      
    </ul>
  

  
</nav>



 </div>
    </header>

    <main id="main" class="main">
      <div class="main-inner">
        <div class="content-wrap">
          <div id="content" class="content">
            

  <div id="posts" class="posts-expand">
    

  

  
  
  

  <article class="post post-type-normal" itemscope itemtype="http://schema.org/Article">
  
  
  
  <div class="post-block">
    <link itemprop="mainEntityOfPage" href="http://chapter007.github.io/blog/blog/2018-01-24-2017-10-05-(Leetcode)KeyboardRow.md">

    <span hidden itemprop="author" itemscope itemtype="http://schema.org/Person">
      <meta itemprop="name" content="zhangjie">
      <meta itemprop="description" content="">
      <meta itemprop="image" content="/blog/images/avatar.jpg">
    </span>

    <span hidden itemprop="publisher" itemscope itemtype="http://schema.org/Organization">
      <meta itemprop="name" content="张杰的日志">
    </span>

    
      <header class="post-header">

        
        
          <h1 class="post-title" itemprop="name headline">(Leetcode)Keyboard Row解题记录</h1>
        

        <div class="post-meta">
          <span class="post-time">
            
              <span class="post-meta-item-icon">
                <i class="fa fa-calendar-o"></i>
              </span>
              
                <span class="post-meta-item-text">发表于</span>
              
              <time title="创建于" itemprop="dateCreated datePublished" datetime="2018-01-24T21:16:48+08:00">
                2018-01-24
              </time>
            

            

            
          </span>

          

          
            
          

          
          

          

          

          

        </div>
      </header>
    

    
    
    
    <div class="post-body" itemprop="articleBody">

      
      

      
        <h2 id="Leetcode-Keyboard-Row解题记录"><a href="#Leetcode-Keyboard-Row解题记录" class="headerlink" title="(Leetcode)Keyboard Row解题记录"></a>(Leetcode)Keyboard Row解题记录</h2><p>这是一题字符串有关的题目，我只想到了笨方法，而且实现起来比较复杂，感觉写出来需要很久</p>
<h1 id="题目"><a href="#题目" class="headerlink" title="题目"></a>题目</h1><pre><code>Given a List of words, return the words that can be typed using letters of alphabet on only one row&apos;s of American keyboard like the image below.

Example 1:

Input: [&quot;Hello&quot;, &quot;Alaska&quot;, &quot;Dad&quot;, &quot;Peace&quot;]
Output: [&quot;Alaska&quot;, &quot;Dad&quot;]


Note:

You may use one character in the keyboard more than once.
You may assume the input string will only contain letters of alphabet.
</code></pre><p>题意是输入一些单词，返回那些字母全在键盘上同一行的单词，比较好懂</p>
<h1 id="解题思路"><a href="#解题思路" class="headerlink" title="解题思路"></a>解题思路</h1><p>思路很清晰，键盘上每一行的字母都是确定的，把每一行都存储到数组里面，然后遍历单词，就可以知道单词的字母在哪一行了，如果所有字母不在同一行则不符合规则。<br>事实上这样的效率会比较低，需要遍历单词，还需要遍历每一行的字母，嵌套遍历了。后来在网上看到别的解法，思路相似，但是使用unordered_set count可以快速得知单词里的字母是否在某一行中。需要补充一些c++的语法知识了。</p>
<h2 id="补充知识"><a href="#补充知识" class="headerlink" title="补充知识"></a>补充知识</h2><h3 id="vector"><a href="#vector" class="headerlink" title="vector"></a>vector</h3><p>vector(向量): C++中的一种数据结构,确切的说是一个类.它相当于一个动态的数组,当程序员无法知道自己需要的数组的规模多大时,用其来解决问题可以达到最大节约空间的目的.</p>
<a id="more"></a>
<p>用法:</p>
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
    
    
    

    

    

    

    <footer class="post-footer">
      

      
      
      

      
        <div class="post-nav">
          <div class="post-nav-next post-nav-item">
            
              <a href="/blog/2018-01-24-2017-10-04-学习java之iterable.md" rel="next" title="学习java之iterable">
                <i class="fa fa-chevron-left"></i> 学习java之iterable
              </a>
            
          </div>

          <span class="post-nav-divider"></span>

          <div class="post-nav-prev post-nav-item">
            
              <a href="/blog/2018-01-24-2017-10-07-学习c++之unordered_set.md" rel="prev" title="学习C++之unordered_set">
                学习C++之unordered_set <i class="fa fa-chevron-right"></i>
              </a>
            
          </div>
        </div>
      

      
      
    </footer>
  </div>
  
  
  
  </article>



    <div class="post-spread">
      
    </div>
  </div>


          </div>
          


          

  



        </div>
        
          
  
  <div class="sidebar-toggle">
    <div class="sidebar-toggle-line-wrap">
      <span class="sidebar-toggle-line sidebar-toggle-line-first"></span>
      <span class="sidebar-toggle-line sidebar-toggle-line-middle"></span>
      <span class="sidebar-toggle-line sidebar-toggle-line-last"></span>
    </div>
  </div>

  <aside id="sidebar" class="sidebar">
    
    <div class="sidebar-inner">

      

      
        <ul class="sidebar-nav motion-element">
          <li class="sidebar-nav-toc sidebar-nav-active" data-target="post-toc-wrap">
            文章目录
          </li>
          <li class="sidebar-nav-overview" data-target="site-overview-wrap">
            站点概览
          </li>
        </ul>
      

      <section class="site-overview-wrap sidebar-panel">
        <div class="site-overview">
          <div class="site-author motion-element" itemprop="author" itemscope itemtype="http://schema.org/Person">
            
              <img class="site-author-image" itemprop="image"
                src="/blog/images/avatar.jpg"
                alt="zhangjie" />
            
              <p class="site-author-name" itemprop="name">zhangjie</p>
              <p class="site-description motion-element" itemprop="description"></p>
          </div>

          <nav class="site-state motion-element">

            
              <div class="site-state-item site-state-posts">
              
                <a href="/blog/archives/">
              
                  <span class="site-state-item-count">17</span>
                  <span class="site-state-item-name">日志</span>
                </a>
              </div>
            

            

            

          </nav>

          

          

          
          

          
          

          

        </div>
      </section>

      
      <!--noindex-->
        <section class="post-toc-wrap motion-element sidebar-panel sidebar-panel-active">
          <div class="post-toc">

            
              
            

            
              <div class="post-toc-content"><ol class="nav"><li class="nav-item nav-level-2"><a class="nav-link" href="#Leetcode-Keyboard-Row解题记录"><span class="nav-number">1.</span> <span class="nav-text">(Leetcode)Keyboard Row解题记录</span></a></li></ol></li><li class="nav-item nav-level-1"><a class="nav-link" href="#题目"><span class="nav-number"></span> <span class="nav-text">题目</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#解题思路"><span class="nav-number"></span> <span class="nav-text">解题思路</span></a><ol class="nav-child"><li class="nav-item nav-level-2"><a class="nav-link" href="#补充知识"><span class="nav-number">1.</span> <span class="nav-text">补充知识</span></a><ol class="nav-child"><li class="nav-item nav-level-3"><a class="nav-link" href="#vector"><span class="nav-number">1.1.</span> <span class="nav-text">vector</span></a></li><li class="nav-item nav-level-3"><a class="nav-link" href="#unordered-set"><span class="nav-number">1.2.</span> <span class="nav-text">unordered_set</span></a></li><li class="nav-item nav-level-3"><a class="nav-link" href="#它的count方法"><span class="nav-number">1.3.</span> <span class="nav-text">它的count方法</span></a></li></ol></li></ol></li><li class="nav-item nav-level-1"><a class="nav-link" href="#AC代码"><span class="nav-number"></span> <span class="nav-text">AC代码</span></a><ol class="nav-child"><li class="nav-item nav-level-3"><a class="nav-link" href="#AC代码理解"><span class="nav-number">0.1.</span> <span class="nav-text">AC代码理解</span></a></li></ol></li></ol></li><li class="nav-item nav-level-1"><a class="nav-link" href="#优化解法"><span class="nav-number"></span> <span class="nav-text">优化解法</span></a><ol class="nav-child"><li class="nav-item nav-level-2"><a class="nav-link" href="#关于优化解法"><span class="nav-number">1.</span> <span class="nav-text">关于优化解法</span></a></li></ol></div>
            

          </div>
        </section>
      <!--/noindex-->
      

      

    </div>
  </aside>


        
      </div>
    </main>

    <footer id="footer" class="footer">
      <div class="footer-inner">
        <div class="copyright">&copy; <span itemprop="copyrightYear">2018</span>
  <span class="with-love">
    <i class="fa fa-user"></i>
  </span>
  <span class="author" itemprop="copyrightHolder">zhangjie</span>

  
</div>


  <div class="powered-by">由 <a class="theme-link" target="_blank" href="https://hexo.io">Hexo</a> 强力驱动</div>



  <span class="post-meta-divider">|</span>



  <div class="theme-info">主题 &mdash; <a class="theme-link" target="_blank" href="https://github.com/iissnan/hexo-theme-next">NexT.Gemini</a> v5.1.4</div>




        







        
      </div>
    </footer>

    
      <div class="back-to-top">
        <i class="fa fa-arrow-up"></i>
        
      </div>
    

    

  </div>

  

<script type="text/javascript">
  if (Object.prototype.toString.call(window.Promise) !== '[object Function]') {
    window.Promise = null;
  }
</script>









  












  
  
    <script type="text/javascript" src="/blog/lib/jquery/index.js?v=2.1.3"></script>
  

  
  
    <script type="text/javascript" src="/blog/lib/fastclick/lib/fastclick.min.js?v=1.0.6"></script>
  

  
  
    <script type="text/javascript" src="/blog/lib/jquery_lazyload/jquery.lazyload.js?v=1.9.7"></script>
  

  
  
    <script type="text/javascript" src="/blog/lib/velocity/velocity.min.js?v=1.2.1"></script>
  

  
  
    <script type="text/javascript" src="/blog/lib/velocity/velocity.ui.min.js?v=1.2.1"></script>
  

  
  
    <script type="text/javascript" src="/blog/lib/fancybox/source/jquery.fancybox.pack.js?v=2.1.5"></script>
  


  


  <script type="text/javascript" src="/blog/js/src/utils.js?v=5.1.4"></script>

  <script type="text/javascript" src="/blog/js/src/motion.js?v=5.1.4"></script>



  
  


  <script type="text/javascript" src="/blog/js/src/affix.js?v=5.1.4"></script>

  <script type="text/javascript" src="/blog/js/src/schemes/pisces.js?v=5.1.4"></script>



  
  <script type="text/javascript" src="/blog/js/src/scrollspy.js?v=5.1.4"></script>
<script type="text/javascript" src="/blog/js/src/post-details.js?v=5.1.4"></script>



  


  <script type="text/javascript" src="/blog/js/src/bootstrap.js?v=5.1.4"></script>



  


  




	





  





  












  





  

  

  

  
  

  

  

  

</body>
</html>
