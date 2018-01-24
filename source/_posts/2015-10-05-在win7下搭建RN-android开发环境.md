---
layout: content
title: 在win7下搭建RN-android开发环境
---

# react-native android开发环境在windows&linux中配置
十一前fb发布了react-native android，当时我听到这个消息就挺兴奋的，准备乘着放假有时间好好玩玩。上了官网，点击start，居然告知only osx！！！并没有苹果设备！难道只能放弃了？先是看了会react js的语法，无意中看到有人在论坛里说在Linux下成功搭建了环境，我想就有戏了

## 资料较少
可能是才发布不久，所以网上的资料并不多，其实动动脑子想想，当时react-native ios需要osx的开发环境，毕竟要开发ios软件嘛，现在要开发android，win/linux环境应该也是可行的，前两天，我在google上找到了一些教程，在教程的指导下完成了win下的开发环境配置，贴一个我觉得写得比较[完整的教程](http://www.cnblogs.com/unofficial/p/4843734.html)，我这篇算是一些补充

## 正题开始

### 准备工作
有几样东西需要先准备好

* 梯子（梯子非常重要）
* jdk环境
* android sdk
* nodejs
* git（并且配置好环境变量）
* react在github的[开源包](https://codeload.github.com/facebook/react-native/zip/master)
准备工作全部做好后才可以继续下面的

### 第一个RN-android-app
* 安装React-native-cli
`npm install -g react-native-cli`
这行代码需要在刚才下载的react开源包里的一个文件夹运行`cd **解压的目录** cd react-native-cli npm install -g`
这样你的react就安装好了
* 初始化第一个项目
`react-native init 项目名`
这个过程会比较慢，对于我家1g内存的老电脑-_-大概用了半个小时
十一后我在学校的pc和自己的笔记本上，搭建这个环境，被这一步坑惨了，其实还是GFW的锅！这个过程其实会联网下载完整的react-native包，之前安装的是cli版，这个包比cli大很多，我就卡死在这里一天半！！！怎么解决呢？如果你也卡死在这里，建议在工程目录里运行`npm install react-native`先手动安装完整包，装好后`npm ls`可以看到装好了的插件，如下图表示你装好了

<img src='http://ww4.sinaimg.cn/mw690/80b7efb6gw1exfr0yzjuoj20n90ltjtl.jpg' width='100%'/>

<img src='http://ww1.sinaimg.cn/mw690/80b7efb6gw1ewq4k1xvimj20j80clmyj.jpg' width='100%'/>

成功后可以看到自动生成了项目，可以看一下目录

<img src='http://ww2.sinaimg.cn/mw690/80b7efb6gw1ewq4d0q3jfj20m60gsn1f.jpg' width='100%'/>

* 运行js服务
在工程目录里执行`node node_modules/react-native/packager/packager.js`
这时候第一次很可能出错（我就是，可能是电脑太老了。。），如下图

<img src='http://ww2.sinaimg.cn/mw690/80b7efb6gw1ewq4de5nftj20j90nogqu.jpg' width='100%'/>

莫慌，只要在执行一下就可以了(*^__^*)，可能是反复多次。。成功后就像下图

<img src='http://ww1.sinaimg.cn/mw690/80b7efb6gw1ewqam12frzj20jw0nx0us.jpg' width='100%'/>

这个时候就可以打开chrome进行一些调试了`http://localhost:8081/debugger-ui`

<img src='http://ww2.sinaimg.cn/mw690/80b7efb6gw1ewq4drt1l9j20rh0bswgj.jpg' width='100%'/>
