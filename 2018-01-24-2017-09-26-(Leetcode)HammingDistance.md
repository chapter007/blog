<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  

  
  <title>(Leetcode)HammingDistance解题记录 | 张杰的日志</title>
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
  <meta name="description" content="算法渣的自我救赎。。作为一个不折不扣的算法渣，在研究生阶段还是多刷刷Leetcode，不然真是找不到工作了哦。今天上午打开Leetcode，挑了一题emmmm，easy+70%通过率，应该能做。然而，事实是残酷的，我又跪了。失败是成功之母，嗯！（这句话真是安慰人的至理名言） 背景知识的补充，c语言中的位运算要能做出这题，必须要用到位运算，而我对这一块的知识是空白的。。。恶补C语言的设计具备了汇编语">
<meta property="og:type" content="article">
<meta property="og:title" content="(Leetcode)HammingDistance解题记录">
<meta property="og:url" content="http://chapter007.github.io/blog/2018-01-24-2017-09-26-(Leetcode)HammingDistance.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="算法渣的自我救赎。。作为一个不折不扣的算法渣，在研究生阶段还是多刷刷Leetcode，不然真是找不到工作了哦。今天上午打开Leetcode，挑了一题emmmm，easy+70%通过率，应该能做。然而，事实是残酷的，我又跪了。失败是成功之母，嗯！（这句话真是安慰人的至理名言） 背景知识的补充，c语言中的位运算要能做出这题，必须要用到位运算，而我对这一块的知识是空白的。。。恶补C语言的设计具备了汇编语">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2017-09-26T11:31:12.626Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(Leetcode)HammingDistance解题记录">
<meta name="twitter:description" content="算法渣的自我救赎。。作为一个不折不扣的算法渣，在研究生阶段还是多刷刷Leetcode，不然真是找不到工作了哦。今天上午打开Leetcode，挑了一题emmmm，easy+70%通过率，应该能做。然而，事实是残酷的，我又跪了。失败是成功之母，嗯！（这句话真是安慰人的至理名言） 背景知识的补充，c语言中的位运算要能做出这题，必须要用到位运算，而我对这一块的知识是空白的。。。恶补C语言的设计具备了汇编语">
  
    <link rel="alternate" href="/blog/atom.xml" title="张杰的日志" type="application/atom+xml">
  
  
    <link rel="icon" href="/favicon.png">
  
  
    <link href="//fonts.googleapis.com/css?family=Source+Code+Pro" rel="stylesheet" type="text/css">
  
  <link rel="stylesheet" href="/blog/css/style.css">
</head>

<body>
  <div id="container">
    <div id="wrap">
      <header id="header">
  <div id="banner"></div>
  <div id="header-outer" class="outer">
    <div id="header-title" class="inner">
      <h1 id="logo-wrap">
        <a href="/blog/" id="logo">张杰的日志</a>
      </h1>
      
        <h2 id="subtitle-wrap">
          <a href="/blog/" id="subtitle">记录学习生活</a>
        </h2>
      
    </div>
    <div id="header-inner" class="inner">
      <nav id="main-nav">
        <a id="main-nav-toggle" class="nav-icon"></a>
        
          <a class="main-nav-link" href="/blog/">Home</a>
        
          <a class="main-nav-link" href="/blog/archives">Archives</a>
        
      </nav>
      <nav id="sub-nav">
        
          <a id="nav-rss-link" class="nav-icon" href="/blog/atom.xml" title="RSS Feed"></a>
        
        <a id="nav-search-btn" class="nav-icon" title="Suche"></a>
      </nav>
      <div id="search-form-wrap">
        <form action="//google.com/search" method="get" accept-charset="UTF-8" class="search-form"><input type="search" name="q" class="search-form-input" placeholder="Search"><button type="submit" class="search-form-submit">&#xF002;</button><input type="hidden" name="sitesearch" value="http://chapter007.github.io/blog"></form>
      </div>
    </div>
  </div>
</header>
      <div class="outer">
        <section id="main"><article id="content-2017-09-26-(Leetcode)HammingDistance" class="article article-type-content" itemscope itemprop="blogPost">
  <div class="article-meta">
    <a href="/blog/2018-01-24-2017-09-26-(Leetcode)HammingDistance.md" class="article-date">
  <time datetime="2018-01-24T13:16:48.207Z" itemprop="datePublished">2018-01-24</time>
</a>
    
  </div>
  <div class="article-inner">
    
    
      <header class="article-header">
        
  
    <h1 class="article-title" itemprop="name">
      (Leetcode)HammingDistance解题记录
    </h1>
  

      </header>
    
    <div class="article-entry" itemprop="articleBody">
      
        <h1 id="算法渣的自我救赎。。"><a href="#算法渣的自我救赎。。" class="headerlink" title="算法渣的自我救赎。。"></a>算法渣的自我救赎。。</h1><p>作为一个不折不扣的算法渣，在研究生阶段还是多刷刷Leetcode，不然真是找不到工作了哦。今天上午打开Leetcode，挑了一题emmmm，easy+70%通过率，应该能做。<br>然而，事实是残酷的，我又跪了。失败是成功之母，嗯！（这句话真是安慰人的至理名言）</p>
<h1 id="背景知识的补充，c语言中的位运算"><a href="#背景知识的补充，c语言中的位运算" class="headerlink" title="背景知识的补充，c语言中的位运算"></a>背景知识的补充，c语言中的位运算</h1><p>要能做出这题，必须要用到位运算，而我对这一块的知识是空白的。。。恶补<br>C语言的设计具备了汇编语言的运算能力，它支持全部的位操作符。位操作符是对字节或字中的位进行测试、置位或移位处理，在对微处理器的编程中，特别适合对寄存器、I/O端口进行操作。<br>6种伟操作符：<br>&lt;&lt;&lt;&lt;&lt;&lt;&lt; HEAD<br>（1） &amp; ：按位“与”——仅当两个操作数为1时，结果为1，否则为0。如：1000 1000  &amp; 1000 0001  = 1000 0000；<br>（2） | ：按位“或”——仅当两个操作数为0时，结果为0，否则为1。如：1000 1000 | 1000 0001 = 1000 1001；<br>（3） ^：按位“异或”——仅当两个操作数不同时，相应的输出结果才为1，否则为0。如：1000 1000 ^ 1000 0001 = 0000 1001 ；<br>（4） ~ ：“取反”——把1置为0，0置为1。如：~1000 1000 = 0111 0111；<br>（5） &lt;&lt;： “左移”——将变量的各位按要求向左移动若干位。如：0000 1000 &lt;&lt;3 = 0100 0000；</p>
<h1 id="（6）-gt-gt-：-“右移”——将变量的各位按要求向右移动若干位。如：0000-1000-gt-gt-3-0000-0001；"><a href="#（6）-gt-gt-：-“右移”——将变量的各位按要求向右移动若干位。如：0000-1000-gt-gt-3-0000-0001；" class="headerlink" title="（6） &gt;&gt;： “右移”——将变量的各位按要求向右移动若干位。如：0000 1000&gt;&gt;3=0000 0001；"></a>（6） &gt;&gt;： “右移”——将变量的各位按要求向右移动若干位。如：0000 1000&gt;&gt;3=0000 0001；</h1><pre><code>（1） &amp; ：按位“与”——仅当两个操作数为1时，结果为1，否则为0。如：1000 1000  &amp; 1000 0001  = 1000 0000；
（2） | ：按位“或”——仅当两个操作数为0时，结果为0，否则为1。如：1000 1000 | 1000 0001 = 1000 1001；
（3） ^：按位“异或”——仅当两个操作数不同时，相应的输出结果才为1，否则为0。
           如：1000 1000 ^ 1000 0001 = 0000 1001 ；
（4） ~ ：“取反”——把1置为0，0置为1。如：~1000 1000 = 0111 0111；
（5） &lt;&lt;： “左移”——将变量的各位按要求向左移动若干位。如：0000 1000 &lt;&lt;3 = 0100 0000；
（6） &gt;&gt;： “右移”——将变量的各位按要求向右移动若干位。如：0000 1000&gt;&gt;3=0000 0001；
</code></pre><blockquote>
<blockquote>
<blockquote>
<blockquote>
<blockquote>
<blockquote>
<blockquote>
<p>5434b6f41f009aeec59c1af4c8dee7c1616c8503<br>基础知识，要记牢了</p>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
<h1 id="题目"><a href="#题目" class="headerlink" title="题目"></a>题目</h1><p>The Hamming distance between two integers is the number of positions at which the corresponding bits are different.</p>
<p>Given two integers x and y, calculate the Hamming distance.</p>
<p>Example：<br>Input: x = 1, y = 4</p>
<p>Output: 2</p>
<p>Explanation:<br>1   (0 0 0 1)<br>4   (0 1 0 0)<br>       ↑   ↑</p>
<p>The above arrows point to positions where the corresponding bits are different.</p>
<p>嗯，题目描述已经够清楚了，我就不解释了。</p>
<h1 id="解题思路"><a href="#解题思路" class="headerlink" title="解题思路"></a>解题思路</h1><p>给的两个数字，对它们进行异或运算（^）后，结果里有几个1，就是Hamming Distance了。为什么这样呢？1和4异或，得到的是6（0001^0100=0101）,把6写成二进制可以看到有两个1.这样答案就出来了</p>
<h1 id="算法"><a href="#算法" class="headerlink" title="算法"></a>算法</h1><pre><code>class Solution {
public:
    int hammingDistance(int x, int y) {
    int res=0;
    int z=x^y;
    for(int i=0;i&lt;32;i++){
        res+=(z&gt;&gt;i)&amp;1;
            //这是遍历z，算出z中1的和
    }
    return res;
    }
};
</code></pre><h1 id="改进"><a href="#改进" class="headerlink" title="改进"></a>改进</h1><p>据说遍历每一位的方法效率并不高，对数字num，使用num&amp;(num-1)可以快速移去bit 1，这样循环num直到为0，循环次数为bit 1的个数，代码也很简单，把上面的for循环换成while</p>
<pre><code>while(num){
    res++;
    num=num&amp;(num-1);
}
</code></pre>
      
    </div>
    <footer class="article-footer">
      <a data-url="http://chapter007.github.io/blog/2018-01-24-2017-09-26-(Leetcode)HammingDistance.md" data-id="cjct5ua100005oou75vxf75cg" class="article-share-link">Teilen</a>
      
      
    </footer>
  </div>
  
    
<nav id="article-nav">
  
    <a href="/blog/2018-01-24-2017-09-26-(Leetcode)ReverseBits.md" id="article-nav-newer" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Neuer</strong>
      <div class="article-nav-title">
        
          (Leetcode)ReverseBits解题记录
        
      </div>
    </a>
  
  
    <a href="/blog/2018-01-24-2017-03-27-北邮软院考研总结.md" id="article-nav-older" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Älter</strong>
      <div class="article-nav-title">北邮软院考研详细总结</div>
    </a>
  
</nav>

  
</article>

</section>
        
          <aside id="sidebar">
  
    

  
    

  
    
  
    
  <div class="widget-wrap">
    <h3 class="widget-title">Archiv</h3>
    <div class="widget">
      <ul class="archive-list"><li class="archive-list-item"><a class="archive-list-link" href="/blog/archives/2018/01/">January 2018</a></li></ul>
    </div>
  </div>


  
    
  <div class="widget-wrap">
    <h3 class="widget-title">letzter Beitrag</h3>
    <div class="widget">
      <ul>
        
          <li>
            <a href="/blog/2018-01-24-2017-10-22-写写日记.md">дд�ռ�</a>
          </li>
        
          <li>
            <a href="/blog/2018-01-24-2017-10-12-学习android之四大核心组件.md">学习android之四大组件</a>
          </li>
        
          <li>
            <a href="/blog/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md">(leetcode)Invert Binary Tree</a>
          </li>
        
          <li>
            <a href="/blog/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md">(leetcode)496. Next Greater Element I</a>
          </li>
        
          <li>
            <a href="/blog/2018-01-24-2017-10-07-学习c++之unordered_set.md">学习C++之unordered_set</a>
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
  
    <a href="/blog/" class="mobile-nav-link">Home</a>
  
    <a href="/blog/archives" class="mobile-nav-link">Archives</a>
  
</nav>
    

<script src="//ajax.googleapis.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>


  <link rel="stylesheet" href="/blog/fancybox/jquery.fancybox.css">
  <script src="/blog/fancybox/jquery.fancybox.pack.js"></script>


<script src="/blog/js/script.js"></script>



  </div>
</body>
</html>