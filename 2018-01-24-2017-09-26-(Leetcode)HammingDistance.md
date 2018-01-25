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










<meta name="description" content="算法渣的自我救赎。。作为一个不折不扣的算法渣，在研究生阶段还是多刷刷Leetcode，不然真是找不到工作了哦。今天上午打开Leetcode，挑了一题emmmm，easy+70%通过率，应该能做。然而，事实是残酷的，我又跪了。失败是成功之母，嗯！（这句话真是安慰人的至理名言） 背景知识的补充，c语言中的位运算要能做出这题，必须要用到位运算，而我对这一块的知识是空白的。。。恶补C语言的设计具备了汇编语">
<meta property="og:type" content="article">
<meta property="og:title" content="(Leetcode)HammingDistance解题记录">
<meta property="og:url" content="http://chapter007.github.io/blog/2018-01-24-2017-09-26-(Leetcode)HammingDistance.md">
<meta property="og:site_name" content="张杰的日志">
<meta property="og:description" content="算法渣的自我救赎。。作为一个不折不扣的算法渣，在研究生阶段还是多刷刷Leetcode，不然真是找不到工作了哦。今天上午打开Leetcode，挑了一题emmmm，easy+70%通过率，应该能做。然而，事实是残酷的，我又跪了。失败是成功之母，嗯！（这句话真是安慰人的至理名言） 背景知识的补充，c语言中的位运算要能做出这题，必须要用到位运算，而我对这一块的知识是空白的。。。恶补C语言的设计具备了汇编语">
<meta property="og:locale" content="zh-Hans">
<meta property="og:updated_time" content="2018-01-25T01:05:19.442Z">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="(Leetcode)HammingDistance解题记录">
<meta name="twitter:description" content="算法渣的自我救赎。。作为一个不折不扣的算法渣，在研究生阶段还是多刷刷Leetcode，不然真是找不到工作了哦。今天上午打开Leetcode，挑了一题emmmm，easy+70%通过率，应该能做。然而，事实是残酷的，我又跪了。失败是成功之母，嗯！（这句话真是安慰人的至理名言） 背景知识的补充，c语言中的位运算要能做出这题，必须要用到位运算，而我对这一块的知识是空白的。。。恶补C语言的设计具备了汇编语">



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



  <link rel="canonical" href="http://chapter007.github.io/blog/2018-01-24-2017-09-26-(Leetcode)HammingDistance.md"/>





  <title>(Leetcode)HammingDistance解题记录 | 张杰的日志</title>
  








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
    <link itemprop="mainEntityOfPage" href="http://chapter007.github.io/blog/blog/2018-01-24-2017-09-26-(Leetcode)HammingDistance.md">

    <span hidden itemprop="author" itemscope itemtype="http://schema.org/Person">
      <meta itemprop="name" content="zhangjie">
      <meta itemprop="description" content="">
      <meta itemprop="image" content="/blog/images/avatar.jpg">
    </span>

    <span hidden itemprop="publisher" itemscope itemtype="http://schema.org/Organization">
      <meta itemprop="name" content="张杰的日志">
    </span>

    
      <header class="post-header">

        
        
          <h1 class="post-title" itemprop="name headline">(Leetcode)HammingDistance解题记录</h1>
        

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

      
      

      
        <h1 id="算法渣的自我救赎。。"><a href="#算法渣的自我救赎。。" class="headerlink" title="算法渣的自我救赎。。"></a>算法渣的自我救赎。。</h1><p>作为一个不折不扣的算法渣，在研究生阶段还是多刷刷Leetcode，不然真是找不到工作了哦。今天上午打开Leetcode，挑了一题emmmm，easy+70%通过率，应该能做。<br>然而，事实是残酷的，我又跪了。失败是成功之母，嗯！（这句话真是安慰人的至理名言）</p>
<h1 id="背景知识的补充，c语言中的位运算"><a href="#背景知识的补充，c语言中的位运算" class="headerlink" title="背景知识的补充，c语言中的位运算"></a>背景知识的补充，c语言中的位运算</h1><p>要能做出这题，必须要用到位运算，而我对这一块的知识是空白的。。。恶补<br>C语言的设计具备了汇编语言的运算能力，它支持全部的位操作符。位操作符是对字节或字中的位进行测试、<br>置位或移位处理，在对微处理器的编程中，特别适合对寄存器、I/O端口进行操作。</p>
<a id="more"></a>
<p>6种伟操作符：<br>（1） &amp; ：按位“与”——仅当两个操作数为1时，结果为1，否则为0。如：1000 1000  &amp; 1000 0001  = 1000 0000；<br>（2） | ：按位“或”——仅当两个操作数为0时，结果为0，否则为1。如：1000 1000 | 1000 0001 = 1000 1001；<br>（3） ^：按位“异或”——仅当两个操作数不同时，相应的输出结果才为1，否则为0。如：1000 1000 ^ 1000 0001 = 0000 1001 ；<br>（4） ~ ：“取反”——把1置为0，0置为1。如：~1000 1000 = 0111 0111；<br>（5） &lt;&lt;： “左移”——将变量的各位按要求向左移动若干位。如：0000 1000 &lt;&lt;3 = 0100 0000；</p>
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
    
    
    

    

    

    

    <footer class="post-footer">
      

      
      
      

      
        <div class="post-nav">
          <div class="post-nav-next post-nav-item">
            
              <a href="/blog/2018-01-24-2017-03-27-北邮软院考研总结.md" rel="next" title="北邮软院考研详细总结">
                <i class="fa fa-chevron-left"></i> 北邮软院考研详细总结
              </a>
            
          </div>

          <span class="post-nav-divider"></span>

          <div class="post-nav-prev post-nav-item">
            
              <a href="/blog/2018-01-24-2017-09-26-(Leetcode)ReverseBits.md" rel="prev" title="(Leetcode)ReverseBits解题记录">
                (Leetcode)ReverseBits解题记录 <i class="fa fa-chevron-right"></i>
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

            
              
            

            
              <div class="post-toc-content"><ol class="nav"><li class="nav-item nav-level-1"><a class="nav-link" href="#算法渣的自我救赎。。"><span class="nav-number">1.</span> <span class="nav-text">算法渣的自我救赎。。</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#背景知识的补充，c语言中的位运算"><span class="nav-number">2.</span> <span class="nav-text">背景知识的补充，c语言中的位运算</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#（6）-gt-gt-：-“右移”——将变量的各位按要求向右移动若干位。如：0000-1000-gt-gt-3-0000-0001；"><span class="nav-number">3.</span> <span class="nav-text">（6） &gt;&gt;： “右移”——将变量的各位按要求向右移动若干位。如：0000 1000&gt;&gt;3=0000 0001；</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#题目"><span class="nav-number">4.</span> <span class="nav-text">题目</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#解题思路"><span class="nav-number">5.</span> <span class="nav-text">解题思路</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#算法"><span class="nav-number">6.</span> <span class="nav-text">算法</span></a></li><li class="nav-item nav-level-1"><a class="nav-link" href="#改进"><span class="nav-number">7.</span> <span class="nav-text">改进</span></a></li></ol></div>
            

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
