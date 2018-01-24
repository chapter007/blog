---
layout: content
title: ubuntu外网ssh配置
---

## 关于ubuntu外网ssh配置，
### 初衷
额，我的初衷说起来有点蛋疼。。我是为了在课上用手机ssh我的笔记本上的ubuntu，然后写python。。。顺便学习linux命令行操作，本教程应该同样适用与其他linux~
### 准备
事实上，linux开启ssh是很简单的是，百度一下也有一堆方法，本教程主要是解决外网访问，这里附送一个[ubuntu开启ssh的教程](http://www.cnblogs.com/xiazh/archive/2010/08/13/1798844.html)，我就不复述了.
其实我的ubuntu好像是默认开启了ssh服务，都没怎么做这一步~

## 正式开始
确定你的ubuntu/linux开启了ssh服务，你可以先用手机/电脑试一下能不能连上，然后再做后面的
> 说下原理，前面的ssh是在同一个局域网内访问的，我们要在别的地方通过手机网络访问，那就要把ssh弄成外网可以访问的状态！所以下面的工作都是路由器的活了

* 打开192.168.1.1（我是TP的），找到ddns，花生壳balabala的，去花生壳注册一个账户，登陆，就如下图，记住这里的域名，这是你外网ssh的地址
<img src="http://ww4.sinaimg.cn/large/80b7efb6gw1exmw83eeinj20xg0iiwfa.jpg" width="80%"/>

* 然后再切到虚拟服务器，添加一个虚拟服务器，如下图,这里的ip地址是你的ubuntu/linux的ip，端口ubuntu ssh默认的是22
<img src="http://ww2.sinaimg.cn/large/80b7efb6gw1exmw83y9uxj20y50ijdgp.jpg" width="80%"/>

这样就ok了，你可以用手机流量试着ssh你的linux系统啦，然后就可以开心的玩了o(^▽^)o

事实上。。我弄好后就完了一下( ╯□╰ )，因为后来发现上课还是要认真听课，不然期末考试复习要累死( ▼-▼ )。。不过我感觉这篇blog还是有意义的(●'◡'●)
