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










<meta name="description" content="继续Leetcode感觉看书上的代码效率并不高，还是写Leetcode比较好 题目Reverse bits of a given 32 bits unsigned integer. For example, given input 43261596 (represented in binary as 00000010100101000001111010011100), return 9641761">
<meta property="og:type" content="article">
<meta property="og:title" content="(Leetcode)ReverseBits解题记录">
<meta property="og:url" content="http://chapter007.github.io/blog/2018-01-24-2017-09-26-(Leetcode)ReverseBits.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="继续Leetcode感觉看书上的代码效率并不高，还是写Leetcode比较好 题目Reverse bits of a given 32 bits unsigned integer. For example, given input 43261596 (represented in binary as 00000010100101000001111010011100), return 9641761">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2017-09-26T11:35:08.765Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(Leetcode)ReverseBits解题记录">
<meta name="twitter:description" content="继续Leetcode感觉看书上的代码效率并不高，还是写Leetcode比较好 题目Reverse bits of a given 32 bits unsigned integer. For example, given input 43261596 (represented in binary as 00000010100101000001111010011100), return 9641761">



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



  <link rel="canonical" href="http://chapter007.github.io/blog/2018-01-24-2017-09-26-(Leetcode)ReverseBits.md"/>





  <title>(Leetcode)ReverseBits解题记录 | 张杰的日志</title>
  








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
    <link itemprop="mainEntityOfPage" href="http://chapter007.github.io/blog/blog/2018-01-24-2017-09-26-(Leetcode)ReverseBits.md">

    <span hidden itemprop="author" itemscope itemtype="http://schema.org/Person">
      <meta itemprop="name" content="zhangjie">
      <meta itemprop="description" content="">
      <meta itemprop="image" content="/blog/images/avatar.jpg">
    </span>

    <span hidden itemprop="publisher" itemscope itemtype="http://schema.org/Organization">
      <meta itemprop="name" content="张杰的日志">
    </span>

    
      <header class="post-header">

        
        
          <h1 class="post-title" itemprop="name headline">(Leetcode)ReverseBits解题记录</h1>
        

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
    
    
    

    

    

    

    <footer class="post-footer">
      

      
      
      

      
        <div class="post-nav">
          <div class="post-nav-next post-nav-item">
            
              <a href="/blog/2018-01-24-2017-09-26-(Leetcode)HammingDistance.md" rel="next" title="(Leetcode)HammingDistance解题记录">
                <i class="fa fa-chevron-left"></i> (Leetcode)HammingDistance解题记录
              </a>
            
          </div>

          <span class="post-nav-divider"></span>

          <div class="post-nav-prev post-nav-item">
            
              <a href="/blog/2018-01-24-2017-09-27-(Leetcode)NumberComplement.md" rel="prev" title="(Leetcode)Number Complement解题记录">
                (Leetcode)Number Complement解题记录 <i class="fa fa-chevron-right"></i>
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

            
              
            

            
              <div class="post-toc-content"><ol class="nav"><li class="nav-item nav-level-1"><a class="nav-link" href="#继续Leetcode"><span class="nav-number">1.</span> <span class="nav-text">继续Leetcode</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#题目"><span class="nav-number">2.</span> <span class="nav-text">题目</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#解题思路"><span class="nav-number">3.</span> <span class="nav-text">解题思路</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#算法"><span class="nav-number">4.</span> <span class="nav-text">算法</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#改进"><span class="nav-number">5.</span> <span class="nav-text">改进</span></a></li></ol></div>
            

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
