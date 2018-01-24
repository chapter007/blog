<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  

  
  <title>(Leetcode)Number Complement解题记录 | 张杰的日志</title>
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
  <meta name="description" content="(Leetcode)Number Complement解题记录又是一题位操作的题目，摩拳擦掌表示应该能做出来。。。不过最后确实是写出来了，不过不是最优解 题目Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary represe">
<meta property="og:type" content="article">
<meta property="og:title" content="(Leetcode)Number Complement解题记录">
<meta property="og:url" content="http://chapter007.github.io/blog/2018-01-24-2017-09-27-(Leetcode)NumberComplement.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="(Leetcode)Number Complement解题记录又是一题位操作的题目，摩拳擦掌表示应该能做出来。。。不过最后确实是写出来了，不过不是最优解 题目Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary represe">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2017-09-30T09:07:34.298Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(Leetcode)Number Complement解题记录">
<meta name="twitter:description" content="(Leetcode)Number Complement解题记录又是一题位操作的题目，摩拳擦掌表示应该能做出来。。。不过最后确实是写出来了，不过不是最优解 题目Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary represe">
  
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
        <section id="main"><article id="content-2017-09-27-(Leetcode)NumberComplement" class="article article-type-content" itemscope itemprop="blogPost">
  <div class="article-meta">
    <a href="/blog/2018-01-24-2017-09-27-(Leetcode)NumberComplement.md" class="article-date">
  <time datetime="2018-01-24T13:16:48.261Z" itemprop="datePublished">2018-01-24</time>
</a>
    
  </div>
  <div class="article-inner">
    
    
      <header class="article-header">
        
  
    <h1 class="article-title" itemprop="name">
      (Leetcode)Number Complement解题记录
    </h1>
  

      </header>
    
    <div class="article-entry" itemprop="articleBody">
      
        <h2 id="Leetcode-Number-Complement解题记录"><a href="#Leetcode-Number-Complement解题记录" class="headerlink" title="(Leetcode)Number Complement解题记录"></a>(Leetcode)Number Complement解题记录</h2><p>又是一题位操作的题目，摩拳擦掌表示应该能做出来。。。不过最后确实是写出来了，不过不是最优解</p>
<h1 id="题目"><a href="#题目" class="headerlink" title="题目"></a>题目</h1><p>Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary representation.</p>
<p>Note:<br>The given integer is guaranteed to fit within the range of a 32-bit signed integer.<br>You could assume no leading zero bit in the integer’s binary representation.</p>
<p>Example：<br>    Input: 5<br>    Output: 2<br>    Explanation: The binary representation of 5 is 101 (no leading zero bits), and its complement is 010. So you need to output 2.</p>
<p>题意是输入一个整数，输出一个十进制数，他们的二进制互补</p>
<h1 id="解题思路"><a href="#解题思路" class="headerlink" title="解题思路"></a>解题思路</h1><p>有了昨天位运算的基础，感觉自己应该能做。首先想到的是先&amp;1，然后再进行移位操作，通过&amp;1是否为0，判断二进制尾位是否为0，然后分情况对输出数字进行移位操作。试了一下发现不可行，比如输入2，二进制是10，互补的应该是01，但是移位出的结果还是10，，，放弃这个想法。<br>后面的思路就比较暴力了，，直接把二进制数转换为十进制的。。比较蠢的方法，不过ac了<br>后来在网上看到比较好的解法，是使用mask掩码，使mask^num就可以得到补码！真是很方便，但是我却想不到，完全没想到这种操作，还是太年轻。。</p>
<h1 id="算法"><a href="#算法" class="headerlink" title="算法"></a>算法</h1><p>比较蠢的方法。。。</p>
<pre><code>class Solution {
public:
    int findComplement(int num) {
        int res=0,i=0;
        int ans[32]={0};
        while(num&gt;0){
            if((num&amp;1)==0){
                ans[i++]=1;
            }else
                ans[i++]=0;
            num&gt;&gt;=1;
        }

        int len=i;
        for(int x=0;x&lt;len;x++){
            res+=ans[x]*pow(2,x);
        }
        return res;
    }
};
</code></pre><h1 id="改进"><a href="#改进" class="headerlink" title="改进"></a>改进</h1><p>使用mask和num异或操作，这样就能得到补码，mask的获取是使用移位操作。<br>mask–1为和num二进制位等长的所有位数为1的数（这是一个规律），与num取^可以得到和num相反的数字</p>
<pre><code>class Solution {
public:
    int findComplement(int num) {
        int temp = num, mask = 1;
        while(temp){
            temp &gt;&gt;= 1;
            mask &lt;&lt;= 1;
        }
        return ((mask - 1) ^ num);
    }
};
</code></pre>
      
    </div>
    <footer class="article-footer">
      <a data-url="http://chapter007.github.io/blog/2018-01-24-2017-09-27-(Leetcode)NumberComplement.md" data-id="cjct5ua100008oou7u8wew8bf" class="article-share-link">Teilen</a>
      
      
    </footer>
  </div>
  
    
<nav id="article-nav">
  
    <a href="/blog/2018-01-24-2017-09-28-学习javaweb之spring.md" id="article-nav-newer" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Neuer</strong>
      <div class="article-nav-title">
        
          学习java-web之spring
        
      </div>
    </a>
  
  
    <a href="/blog/2018-01-24-2017-09-26-(Leetcode)ReverseBits.md" id="article-nav-older" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Älter</strong>
      <div class="article-nav-title">(Leetcode)ReverseBits解题记录</div>
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