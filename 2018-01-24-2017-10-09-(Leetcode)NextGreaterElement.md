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










<meta name="description" content="(leetcode)496. Next Greater Element I题目You are given two arrays (without duplicates) nums1 and nums2 where nums1’s elements are subset of nums2. Find all the next greater numbers for nums1&amp;apos;s elem">
<meta property="og:type" content="article">
<meta property="og:title" content="(leetcode)496. Next Greater Element I">
<meta property="og:url" content="http://chapter007.github.io/blog/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="(leetcode)496. Next Greater Element I题目You are given two arrays (without duplicates) nums1 and nums2 where nums1’s elements are subset of nums2. Find all the next greater numbers for nums1&amp;apos;s elem">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2018-01-24T15:31:04.997Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(leetcode)496. Next Greater Element I">
<meta name="twitter:description" content="(leetcode)496. Next Greater Element I题目You are given two arrays (without duplicates) nums1 and nums2 where nums1’s elements are subset of nums2. Find all the next greater numbers for nums1&amp;apos;s elem">



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



  <link rel="canonical" href="http://chapter007.github.io/blog/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md"/>





  <title>(leetcode)496. Next Greater Element I | 张杰的日志</title>
  








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
    <link itemprop="mainEntityOfPage" href="http://chapter007.github.io/blog/blog/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md">

    <span hidden itemprop="author" itemscope itemtype="http://schema.org/Person">
      <meta itemprop="name" content="zhangjie">
      <meta itemprop="description" content="">
      <meta itemprop="image" content="/blog/images/avatar.jpg">
    </span>

    <span hidden itemprop="publisher" itemscope itemtype="http://schema.org/Organization">
      <meta itemprop="name" content="张杰的日志">
    </span>

    
      <header class="post-header">

        
        
          <h1 class="post-title" itemprop="name headline">(leetcode)496. Next Greater Element I</h1>
        

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

      
      

      
        <h2 id="leetcode-496-Next-Greater-Element-I"><a href="#leetcode-496-Next-Greater-Element-I" class="headerlink" title="(leetcode)496. Next Greater Element I"></a>(leetcode)496. Next Greater Element I</h2><h1 id="题目"><a href="#题目" class="headerlink" title="题目"></a>题目</h1><pre><code>You are given two arrays (without duplicates) nums1 and nums2 where nums1’s elements are subset of nums2. Find all the next greater numbers for nums1&apos;s elements in the corresponding places of nums2.

The Next Greater Number of a number x in nums1 is the first greater number to its right in nums2. If it does not exist, output -1 for this number.

Example 1:
Input: nums1 = [4,1,2], nums2 = [1,3,4,2].
Output: [-1,3,-1]
Explanation:
    For number 4 in the first array, you cannot find the next greater number for it in the second array, so output -1.
    For number 1 in the first array, the next greater number for it in the second array is 3.
    For number 2 in the first array, there is no next greater number for it in the second array, so output -1.
Example 2:
Input: nums1 = [2,4], nums2 = [1,2,3,4].
Output: [3,-1]
Explanation:
    For number 2 in the first array, the next greater number for it in the second array is 3.
    For number 4 in the first array, there is no next greater number for it in the second array, so output -1.
Note:
All elements in nums1 and nums2 are unique.
The length of both nums1 and nums2 would not exceed 1000.
</code></pre><p>这题下午在看的时候感觉能做，晚上回来就被打脸了。。。我能想到的解法自然是比较基础的遍历两个数组，从第一个数组中拿一个数到第二个数组中做比较，先是找到这个数字，然后看这个数字后面有没有比它更大的数字，如果有，就放到结果集里，如果没有，就放-1到结果集中。</p>
<a id="more"></a>
<p>事实上，两层嵌套的遍历会带来很多问题。<br>我的天那。。。东拼西凑凑出来了。。。今晚不想写了，明天在看大佬的解法吧</p>
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
    
    
    

    

    

    

    <footer class="post-footer">
      

      
      
      

      
        <div class="post-nav">
          <div class="post-nav-next post-nav-item">
            
              <a href="/blog/2018-01-24-2017-10-07-学习c++之unordered_set.md" rel="next" title="学习C++之unordered_set">
                <i class="fa fa-chevron-left"></i> 学习C++之unordered_set
              </a>
            
          </div>

          <span class="post-nav-divider"></span>

          <div class="post-nav-prev post-nav-item">
            
              <a href="/blog/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md" rel="prev" title="(leetcode)Invert Binary Tree">
                (leetcode)Invert Binary Tree <i class="fa fa-chevron-right"></i>
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

            
              
            

            
              <div class="post-toc-content"><ol class="nav"><li class="nav-item nav-level-2"><a class="nav-link" href="#leetcode-496-Next-Greater-Element-I"><span class="nav-number">1.</span> <span class="nav-text">(leetcode)496. Next Greater Element I</span></a></li></ol></li><li class="nav-item nav-level-1"><a class="nav-link" href="#题目"><span class="nav-number"></span> <span class="nav-text">题目</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#AC代码"><span class="nav-number"></span> <span class="nav-text">AC代码</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#大神的代码"><span class="nav-number"></span> <span class="nav-text">大神的代码</span></a><ol class="nav-child"><li class="nav-item nav-level-2"><a class="nav-link" href="#解释的不是很明白，这个做法很难想到啊"><span class="nav-number">1.</span> <span class="nav-text">解释的不是很明白，这个做法很难想到啊</span></a></li></ol></div>
            

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
