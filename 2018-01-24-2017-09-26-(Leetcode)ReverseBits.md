<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  

  
  <title>(Leetcode)ReverseBits解题记录 | 张杰的日志</title>
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
  <meta name="description" content="继续Leetcode感觉看书上的代码效率并不高，还是写Leetcode比较好 题目Reverse bits of a given 32 bits unsigned integer. For example, given input 43261596 (represented in binary as 00000010100101000001111010011100), return 9641761">
<meta property="og:type" content="article">
<meta property="og:title" content="(Leetcode)ReverseBits解题记录">
<meta property="og:url" content="http://yoursite.com/2018-01-24-2017-09-26-(Leetcode)ReverseBits.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="继续Leetcode感觉看书上的代码效率并不高，还是写Leetcode比较好 题目Reverse bits of a given 32 bits unsigned integer. For example, given input 43261596 (represented in binary as 00000010100101000001111010011100), return 9641761">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2017-09-26T11:35:08.765Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(Leetcode)ReverseBits解题记录">
<meta name="twitter:description" content="继续Leetcode感觉看书上的代码效率并不高，还是写Leetcode比较好 题目Reverse bits of a given 32 bits unsigned integer. For example, given input 43261596 (represented in binary as 00000010100101000001111010011100), return 9641761">
  
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
        <section id="main"><article id="content-2017-09-26-(Leetcode)ReverseBits" class="article article-type-content" itemscope itemprop="blogPost">
  <div class="article-meta">
    <a href="/2018-01-24-2017-09-26-(Leetcode)ReverseBits.md" class="article-date">
  <time datetime="2018-01-24T13:16:48.222Z" itemprop="datePublished">2018-01-24</time>
</a>
    
  </div>
  <div class="article-inner">
    
    
      <header class="article-header">
        
  
    <h1 class="article-title" itemprop="name">
      (Leetcode)ReverseBits解题记录
    </h1>
  

      </header>
    
    <div class="article-entry" itemprop="articleBody">
      
        <h1 id="继续Leetcode"><a href="#继续Leetcode" class="headerlink" title="继续Leetcode"></a>继续Leetcode</h1><p>感觉看书上的代码效率并不高，还是写Leetcode比较好</p>
<h1 id="题目"><a href="#题目" class="headerlink" title="题目"></a>题目</h1><p>Reverse bits of a given 32 bits unsigned integer.</p>
<p>For example, given input 43261596 (represented in binary as 00000010100101000001111010011100), return 964176192 (represented in binary as 00111001011110000010100101000000).</p>
<p>Follow up:<br>If this function is called many times, how would you optimize it?</p>
<p>Related problem: Reverse Integer</p>
<p>题意是给定一个32位无符号的整数，然后反转这个数的二进制形式，得到一个新的32位无符号整数，注意这是十进制的</p>
<h1 id="解题思路"><a href="#解题思路" class="headerlink" title="解题思路"></a>解题思路</h1><p>有了前面的Hamming Distance基础，可以联想到这题应该也是用位运算。不过，我只想到了把无符号整数&amp;1，可以快速得到2进制的数，但是我那样还要转换回十进制。。。做了一会，还是跪了。在网上找到别的方法，使用位运算的左右移位操作即可实现这个要求。<br>当给定的数字n,最后一位n&amp;1==1，则把要输出的数 m&gt;&gt;1+1,如果n&amp;1==0，则m&gt;&gt;1,这个操作是在一个32次循环中<br>因为32位数字，每次操作后n需要右移一位n&lt;&lt;=1</p>
<h1 id="算法"><a href="#算法" class="headerlink" title="算法"></a>算法</h1><pre><code>class Solution {
public:
    uint32_t reverseBits(uint32_t n) {
        uint32_t m=0;
        for(int i=0;i&lt;32;i++){
            if((n&amp;1)==1){
                m=(m&lt;&lt;1)+1;
                n&gt;&gt;=1;
            }else{
                m=m&lt;&lt;1;
                n&gt;&gt;=1;
            }
        }
        return m;
    }
};
</code></pre><h1 id="改进"><a href="#改进" class="headerlink" title="改进"></a>改进</h1><p>在Leetcode的discuss里看到的o(1)解法，给跪了。。。不过我倒是没看懂</p>
<pre><code>class Solution {
public:
    uint32_t reverseBits(uint32_t n) {
        n = (n &gt;&gt; 16) | (n &lt;&lt; 16);
        n = ((n &amp; 0xff00ff00) &gt;&gt; 8) | ((n &amp; 0x00ff00ff) &lt;&lt; 8);
        n = ((n &amp; 0xf0f0f0f0) &gt;&gt; 4) | ((n &amp; 0x0f0f0f0f) &lt;&lt; 4);
        n = ((n &amp; 0xcccccccc) &gt;&gt; 2) | ((n &amp; 0x33333333) &lt;&lt; 2);
        n = ((n &amp; 0xaaaaaaaa) &gt;&gt; 1) | ((n &amp; 0x55555555) &lt;&lt; 1);
        return n;
    }
};
</code></pre>
      
    </div>
    <footer class="article-footer">
      <a data-url="http://yoursite.com/2018-01-24-2017-09-26-(Leetcode)ReverseBits.md" data-id="cjct4js3m000728u73shhp9mb" class="article-share-link">Teilen</a>
      
      
    </footer>
  </div>
  
    
<nav id="article-nav">
  
    <a href="/2018-01-24-2017-09-27-(Leetcode)NumberComplement.md" id="article-nav-newer" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Neuer</strong>
      <div class="article-nav-title">
        
          (Leetcode)Number Complement解题记录
        
      </div>
    </a>
  
  
    <a href="/2018-01-24-2017-09-26-(Leetcode)HammingDistance.md" id="article-nav-older" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Älter</strong>
      <div class="article-nav-title">(Leetcode)HammingDistance解题记录</div>
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