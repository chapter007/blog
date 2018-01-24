<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  

  
  <title>(leetcode)496. Next Greater Element I | 张杰的日志</title>
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
  <meta name="description" content="(leetcode)496. Next Greater Element I题目You are given two arrays (without duplicates) nums1 and nums2 where nums1’s elements are subset of nums2. Find all the next greater numbers for nums1’s elements">
<meta property="og:type" content="article">
<meta property="og:title" content="(leetcode)496. Next Greater Element I">
<meta property="og:url" content="http://yoursite.com/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="(leetcode)496. Next Greater Element I题目You are given two arrays (without duplicates) nums1 and nums2 where nums1’s elements are subset of nums2. Find all the next greater numbers for nums1’s elements">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2017-10-11T07:16:29.370Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(leetcode)496. Next Greater Element I">
<meta name="twitter:description" content="(leetcode)496. Next Greater Element I题目You are given two arrays (without duplicates) nums1 and nums2 where nums1’s elements are subset of nums2. Find all the next greater numbers for nums1’s elements">
  
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
        <section id="main"><article id="content-2017-10-09-(Leetcode)NextGreaterElement" class="article article-type-content" itemscope itemprop="blogPost">
  <div class="article-meta">
    <a href="/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md" class="article-date">
  <time datetime="2018-01-24T13:16:48.369Z" itemprop="datePublished">2018-01-24</time>
</a>
    
  </div>
  <div class="article-inner">
    
    
      <header class="article-header">
        
  
    <h1 class="article-title" itemprop="name">
      (leetcode)496. Next Greater Element I
    </h1>
  

      </header>
    
    <div class="article-entry" itemprop="articleBody">
      
        <h2 id="leetcode-496-Next-Greater-Element-I"><a href="#leetcode-496-Next-Greater-Element-I" class="headerlink" title="(leetcode)496. Next Greater Element I"></a>(leetcode)496. Next Greater Element I</h2><h1 id="题目"><a href="#题目" class="headerlink" title="题目"></a>题目</h1><p>You are given two arrays (without duplicates) nums1 and nums2 where nums1’s elements are subset of nums2. Find all the next greater numbers for nums1’s elements in the corresponding places of nums2.</p>
<p>The Next Greater Number of a number x in nums1 is the first greater number to its right in nums2. If it does not exist, output -1 for this number.</p>
<p>Example 1:<br>Input: nums1 = [4,1,2], nums2 = [1,3,4,2].<br>Output: [-1,3,-1]<br>Explanation:<br>    For number 4 in the first array, you cannot find the next greater number for it in the second array, so output -1.<br>    For number 1 in the first array, the next greater number for it in the second array is 3.<br>    For number 2 in the first array, there is no next greater number for it in the second array, so output -1.<br>Example 2:<br>Input: nums1 = [2,4], nums2 = [1,2,3,4].<br>Output: [3,-1]<br>Explanation:<br>    For number 2 in the first array, the next greater number for it in the second array is 3.<br>    For number 4 in the first array, there is no next greater number for it in the second array, so output -1.<br>Note:<br>All elements in nums1 and nums2 are unique.<br>The length of both nums1 and nums2 would not exceed 1000.<br>这题下午在看的时候感觉能做，晚上回来就被打脸了。。。我能想到的解法自然是比较基础的遍历两个数组，从第一个数组中拿一个数到第二个数组中做比较，先是找到这个数字，然后看这个数字后面有没有比它更大的数字，如果有，就放到结果集里，如果没有，就放-1到结果集中。<br>事实上，两层嵌套的遍历会带来很多问题。<br>我的天那。。。东拼西凑凑出来了。。。今晚不想写了，明天在看大佬的解法吧</p>
<h1 id="AC代码"><a href="#AC代码" class="headerlink" title="AC代码"></a>AC代码</h1><pre><code>class Solution {
public:
    vector&lt;int&gt; nextGreaterElement(vector&lt;int&gt;&amp; findNums, vector&lt;int&gt;&amp; nums) {
        vector&lt;int&gt; res;

        for(int i=0;i&lt;findNums.size();i++){
            bool flag=false;
            for(int j=0;j&lt;nums.size();j++){
                if(findNums[i]==nums[j]){
                    for(int x=j;x&lt;nums.size();x++){
                        if(findNums[i]&lt;nums[x+1]&amp;&amp;x+1&lt;nums.size()){
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
</code></pre><p>方法和我上面说的一样，实现起来比较麻烦，嵌套了好几层for循环，效率很低，虽然强行ac了</p>
<h1 id="大神的代码"><a href="#大神的代码" class="headerlink" title="大神的代码"></a>大神的代码</h1><pre><code>class Solution {
public:
    vector&lt;int&gt; nextGreaterElement(vector&lt;int&gt;&amp; findNums, vector&lt;int&gt;&amp; nums) {
        stack&lt;int&gt; s;
        unordered_map&lt;int, int&gt; m;
        for (int n : nums) {
            while (s.size() &amp;&amp; s.top() &lt; n) {
                m[s.top()] = n;
                s.pop();
            }
            s.push(n);
        }
        vector&lt;int&gt; ans;
        for (int n : findNums) ans.push_back(m.count(n) ? m[n] : -1);
        return ans;
    }
};
</code></pre><p>可见使用了stack和unordered_map这两个数据类型（虽然前面已经做过不少几次这些数据类型的题了，但是我还是难以主动使用）<br>map 用来存放nums里面的数字，stack起到了一个中间商的作用<br>在while循环中，把符合条件的数字存储到了map里面。当第一个for循环结束的时候，就已经把nums里的数字归好类了。因为findnums是nums的子集，再遍历一次findnums就可以轻松的写出答案。<br>关键点是第一个for循环，其实按照题目规则，比如【1，3，4，2】这个序列，只有1有Greater num，是3。。</p>
<h2 id="解释的不是很明白，这个做法很难想到啊"><a href="#解释的不是很明白，这个做法很难想到啊" class="headerlink" title="解释的不是很明白，这个做法很难想到啊"></a>解释的不是很明白，这个做法很难想到啊</h2>
      
    </div>
    <footer class="article-footer">
      <a data-url="http://yoursite.com/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md" data-id="cjct4js4b000d28u71h67jwjh" class="article-share-link">Teilen</a>
      
      
    </footer>
  </div>
  
    
<nav id="article-nav">
  
    <a href="/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md" id="article-nav-newer" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Neuer</strong>
      <div class="article-nav-title">
        
          (leetcode)Invert Binary Tree
        
      </div>
    </a>
  
  
    <a href="/2018-01-24-2017-10-07-学习c++之unordered_set.md" id="article-nav-older" class="article-nav-link-wrap">
      <strong class="article-nav-caption">Älter</strong>
      <div class="article-nav-title">学习C++之unordered_set</div>
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