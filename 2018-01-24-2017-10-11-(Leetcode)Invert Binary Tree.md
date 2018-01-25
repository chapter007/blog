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










<meta name="description" content="(leetcode)Invert Binary Tree#一些废话这题就是传说中那个难倒那个大牛的一题，反转二叉树。其实我看到题也不会，慢慢积累吧。 题目Invert a binary tree.      4    /   \   2     7  / \   / \ 1   3 6   9 to     4    /   \   7     2  / \   / \ 9   6 3   1">
<meta property="og:type" content="article">
<meta property="og:title" content="(leetcode)Invert Binary Tree">
<meta property="og:url" content="http://chapter007.github.io/blog/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="(leetcode)Invert Binary Tree#一些废话这题就是传说中那个难倒那个大牛的一题，反转二叉树。其实我看到题也不会，慢慢积累吧。 题目Invert a binary tree.      4    /   \   2     7  / \   / \ 1   3 6   9 to     4    /   \   7     2  / \   / \ 9   6 3   1">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2018-01-24T15:29:34.856Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(leetcode)Invert Binary Tree">
<meta name="twitter:description" content="(leetcode)Invert Binary Tree#一些废话这题就是传说中那个难倒那个大牛的一题，反转二叉树。其实我看到题也不会，慢慢积累吧。 题目Invert a binary tree.      4    /   \   2     7  / \   / \ 1   3 6   9 to     4    /   \   7     2  / \   / \ 9   6 3   1">



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



  <link rel="canonical" href="http://chapter007.github.io/blog/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md"/>





  <title>(leetcode)Invert Binary Tree | 张杰的日志</title>
  








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
    <link itemprop="mainEntityOfPage" href="http://chapter007.github.io/blog/blog/2018-01-24-2017-10-11-(Leetcode)Invert Binary Tree.md">

    <span hidden itemprop="author" itemscope itemtype="http://schema.org/Person">
      <meta itemprop="name" content="zhangjie">
      <meta itemprop="description" content="">
      <meta itemprop="image" content="/blog/images/avatar.jpg">
    </span>

    <span hidden itemprop="publisher" itemscope itemtype="http://schema.org/Organization">
      <meta itemprop="name" content="张杰的日志">
    </span>

    
      <header class="post-header">

        
        
          <h1 class="post-title" itemprop="name headline">(leetcode)Invert Binary Tree</h1>
        

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

      
      

      
        <h2 id="leetcode-Invert-Binary-Tree"><a href="#leetcode-Invert-Binary-Tree" class="headerlink" title="(leetcode)Invert Binary Tree"></a>(leetcode)Invert Binary Tree</h2><p>#一些废话<br>这题就是传说中那个难倒那个大牛的一题，反转二叉树。其实我看到题也不会，慢慢积累吧。</p>
<h1 id="题目"><a href="#题目" class="headerlink" title="题目"></a>题目</h1><p>Invert a binary tree.</p>
<pre><code>     4
   /   \
  2     7
 / \   / \
1   3 6   9
</code></pre><p>to</p>
<pre><code>    4
   /   \
  7     2
 / \   / \
9   6 3   1

Google: 90% of our engineers use the software you wrote (Homebrew), but you can’t invert a binary tree on a whiteboard so fuck off.
</code></pre><a id="more"></a>
<p>题意通过例子很容易懂，就是交换二叉树的左右节点，这题有递归和非递归两种方法，都不难实现</p>
<h1 id="AC代码"><a href="#AC代码" class="headerlink" title="AC代码"></a>AC代码</h1><p>递归版本：</p>
<pre><code>class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        if(root){
            invertTree(root-&gt;left);
            invertTree(root-&gt;right);
            swap(root-&gt;left,root-&gt;right);
        }
        return root;
    }
};
</code></pre><p>非递归版本：</p>
<pre><code>class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        stack&lt;TreeNode*&gt; s;
        s.push(root);
        while(!s.empty()){
            TreeNode* p=s.top();
            s.pop();
            if(p){
                s.push(p-&gt;left);
                s.push(p-&gt;right);
                swap(p-&gt;left,p-&gt;right);
            }
        }
        return root;
    }
};
</code></pre><p>递归版本的代码更加简洁，但是不是很容易理解，emmm一层层的循环嵌套让我有点晕。非递归的版本使用了栈，就是树的遍历，在遍历的过程中交换了左右节点。</p>
<h1 id="关于以后的一些想法"><a href="#关于以后的一些想法" class="headerlink" title="关于以后的一些想法"></a>关于以后的一些想法</h1><p>其实在考研结束以后，我就开始纠结这个问题了。以后是做安卓开发还是web开发，还是学习大数据，数据挖掘这类？想了很久，直到今天。看了一些博客，一些论坛上的讨论，有点想法了。</p>
<ul>
<li>不管以后想做什么，算法始终是基础，基础就是牢固了学别的都很快。算法不仅是基础，也是面试必考的内容！所以学习算法是首要任务</li>
<li>除了算法以外，操作系统，计算机网络，数据库也是基础，这些知识也需要牢固！</li>
<li>关于是学习安卓还是web，或是大数据，我都可以接触一下，其实安卓和web以前已经有一定的基础了。</li>
</ul>

      
    </div>
    
    
    

    

    

    

    <footer class="post-footer">
      

      
      
      

      
        <div class="post-nav">
          <div class="post-nav-next post-nav-item">
            
              <a href="/blog/2018-01-24-2017-10-09-(Leetcode)NextGreaterElement.md" rel="next" title="(leetcode)496. Next Greater Element I">
                <i class="fa fa-chevron-left"></i> (leetcode)496. Next Greater Element I
              </a>
            
          </div>

          <span class="post-nav-divider"></span>

          <div class="post-nav-prev post-nav-item">
            
              <a href="/blog/2018-01-24-2017-10-12-学习android之四大核心组件.md" rel="prev" title="学习android之四大组件">
                学习android之四大组件 <i class="fa fa-chevron-right"></i>
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

            
              
            

            
              <div class="post-toc-content"><ol class="nav"><li class="nav-item nav-level-2"><a class="nav-link" href="#leetcode-Invert-Binary-Tree"><span class="nav-number">1.</span> <span class="nav-text">(leetcode)Invert Binary Tree</span></a></li></ol></li><li class="nav-item nav-level-1"><a class="nav-link" href="#题目"><span class="nav-number"></span> <span class="nav-text">题目</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#AC代码"><span class="nav-number"></span> <span class="nav-text">AC代码</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#关于以后的一些想法"><span class="nav-number"></span> <span class="nav-text">关于以后的一些想法</span></a></div>
            

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
