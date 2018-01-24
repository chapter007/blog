<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  

  
  <title>(leetcode)Invert Binary Tree | 张杰的日志</title>
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
  <meta name="description" content="(leetcode)Invert Binary Tree#一些废话这题就是传说中那个难倒那个大牛的一题，反转二叉树。其实我看到题也不会，慢慢积累吧。 题目Invert a binary tree. 4    /   \  2     7 / \   / \1   3 6   9to     4   /   \  7     2 / \   / \9   6 3   1 Google: 90% of">
<meta property="og:type" content="article">
<meta property="og:title" content="(leetcode)Invert Binary Tree">
<meta property="og:url" content="http://yoursite.com/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="(leetcode)Invert Binary Tree#一些废话这题就是传说中那个难倒那个大牛的一题，反转二叉树。其实我看到题也不会，慢慢积累吧。 题目Invert a binary tree. 4    /   \  2     7 / \   / \1   3 6   9to     4   /   \  7     2 / \   / \9   6 3   1 Google: 90% of">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2017-10-11T07:47:11.617Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(leetcode)Invert Binary Tree">
<meta name="twitter:description" content="(leetcode)Invert Binary Tree#一些废话这题就是传说中那个难倒那个大牛的一题，反转二叉树。其实我看到题也不会，慢慢积累吧。 题目Invert a binary tree. 4    /   \  2     7 / \   / \1   3 6   9to     4   /   \  7     2 / \   / \9   6 3   1 Google: 90% of">
  
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
        <section id="main"><article id="content-2017-10-11-(Leetcode)Invert Binary Tree" class="article article-type-content" itemscope itemprop="blogPost">
  <div class="article-meta">
    <a href="/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md" class="article-date">
  <time datetime="2018-01-24T13:16:48.390Z" itemprop="datePublished">2018-01-24</time>
</a>
    
  </div>
  <div class="article-inner">
    
    
      <header class="article-header">
        
  
    <h1 class="article-title" itemprop="name">
      (leetcode)Invert Binary Tree
    </h1>
  

      </header>
    
    <div class="article-entry" itemprop="articleBody">
      
        <h2 id="leetcode-Invert-Binary-Tree"><a href="#leetcode-Invert-Binary-Tree" class="headerlink" title="(leetcode)Invert Binary Tree"></a>(leetcode)Invert Binary Tree</h2><p>#一些废话<br>这题就是传说中那个难倒那个大牛的一题，反转二叉树。其实我看到题也不会，慢慢积累吧。</p>
<h1 id="题目"><a href="#题目" class="headerlink" title="题目"></a>题目</h1><p>Invert a binary tree.</p>
<pre><code>4
</code></pre><p>   /   \<br>  2     7<br> / \   / \<br>1   3 6   9<br>to<br>     4<br>   /   \<br>  7     2<br> / \   / \<br>9   6 3   1</p>
<pre><code>Google: 90% of our engineers use the software you wrote (Homebrew), but you can’t invert a binary tree on a whiteboard so fuck off.
</code></pre><p>题意通过例子很容易懂，就是交换二叉树的左右节点，这题有递归和非递归两种方法，都不难实现</p>
<h1 id="AC代码"><a href="#AC代码" class="headerlink" title="AC代码"></a>AC代码</h1><p>递归版本：<br>    class Solution {<br>    public:<br>        TreeNode<em> invertTree(TreeNode</em> root) {<br>            if(root){<br>                invertTree(root-&gt;left);<br>                invertTree(root-&gt;right);<br>                swap(root-&gt;left,root-&gt;right);<br>            }<br>            return root;<br>        }<br>    };</p>
<p>非递归版本：<br>    class Solution {<br>    public:<br>        TreeNode<em> invertTree(TreeNode</em> root) {<br>            stack<treenode*> s;<br>            s.push(root);<br>            while(!s.empty()){<br>                TreeNode* p=s.top();<br>                s.pop();<br>                if(p){<br>                    s.push(p-&gt;left);<br>                    s.push(p-&gt;right);<br>                    swap(p-&gt;left,p-&gt;right);<br>                }<br>            }<br>            return root;<br>        }<br>    };</treenode*></p>
<p>递归版本的代码更加简洁，但是不是很容易理解，emmm一层层的循环嵌套让我有点晕。非递归的版本使用了栈，就是树的遍历，在遍历的过程中交换了左右节点。</p>
<h1 id="关于以后的一些想法"><a href="#关于以后的一些想法" class="headerlink" title="关于以后的一些想法"></a>关于以后的一些想法</h1><p>其实在考研结束以后，我就开始纠结这个问题了。以后是做安卓开发还是web开发，还是学习大数据，数据挖掘这类？想了很久，直到今天。看了一些博客，一些论坛上的讨论，有点想法了。</p>
<ul>
<li>不管以后想做什么，算法始终是基础，基础就是牢固了学别的都很快。算法不仅是基础，也是面试必考的内容！所以学习算法是首要任务</li>
<li>除了算法以外，操作系统，计算机网络，数据库也是基础，这些知识也需要牢固！</li>
<li>关于是学习安卓还是web，或是大数据，我都可以接触一下，其实安卓和web以前已经有一定的基础了。</li>
</ul>

      
    </div>
    <footer class="article-footer">
      <a data-url="http://yoursite.com/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md" data-id="cjct4js4d000e28u7k9xrygzk" class="article-share-link">Teilen</a>
      
      
    </footer>
  </div>
  
    
<nav id="article-nav">
  
    <a href="/2018-01-24-2017-10-12-学习android之四大核心组件.md" id="article-nav-newer" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Neuer</strong>
      <div class="article-nav-title">
        
          学习android之四大组件
        
      </div>
    </a>
  
  
    <a href="/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md" id="article-nav-older" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Älter</strong>
      <div class="article-nav-title">(leetcode)496. Next Greater Element I</div>
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