---
layout: content
title: 学习java-web之spring
---

# 学习java-web之spring
按照我们组的学习计划，emmmm，明明是安卓开发小组，怎么变成学习java web了？？我也不是很懂，可能是实验室用到的java web会比较多吧。
那学就学吧，多学点总是没坏处的，其实是今天不太想做Leetcode了（手动滑稽）。
看了一下学习计划，最后任务是使用任一个框架做一个Login的demo，考虑到spring框架那么有名气，那就学习一下吧~
## 学习步骤
考虑到我也是有一定java开发基础了，就直接去github下一个demo回来看看吧，感觉那样会学的比较快，嗯。
在github很容易就可以搜索到相关的项目，关键词‘java spring Login demo’。down下来后用idea打开，会自动下载需要的框架等等，待他下好就可以工作了。
第一个下载的demo有问题，又找了一个成功跑了起来,这里放图片太麻烦了，自行脑补吧。接下来就看看代码是如何实现的。
## 学习代码
emmmm，这个代码有点复杂哈，不仅实现了简单的登录和退出，还有注册等内容，所以。。我还是准备找个教程来学习吧~

## 29号继续学习spring
昨天开始，就疯狂报错！很气，主要是java.lang.ClassNotFoundException: org.apache.commons.dbcp.BasicDataSource这个错，嗯，应该是少了一个jar包，在网上找了一下，据说除了common这个包还有一个commons-pool.jar这个包！
哇，心态蹦了！！！找了这些个文件添加到library里，还是报错。
还是没弄好，感觉是和版本有一定关系，mmp终于好了，但是又有另外一个问题了。。错误原因是版本不对，必须是1.2.2版本commons-pool必须是1.3
哇！终于搞定了！这个简单的demo，我还是费了不少时间哈哈

## 总结一下有哪些坑吧
* 首先是上午那个缺少类的问题，注意版本，还有就是用idea的话，添加新的包，可以选择maven添加，这样可以在线搜索添加，很方便
* 还有就是注解，在controller类上要加上@Controller注解，在service impl上加上@service 还有别的，就看代码吧
* 编码也有一个坑。。。默认情况下，post过来的中文会乱码，在网上找到解决办法，挺有效的，在web.xml中加上
	<filter>
			<filter-name>CharacterEncodingFilter</filter-name>
			<filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
			<init-param>
				<param-name>encoding</param-name>
				<param-value>utf-8</param-value>
			</init-param>
		</filter>
		<filter-mapping>
			<filter-name>CharacterEncodingFilter</filter-name>
			<url-pattern>/*</url-pattern>
		</filter-mapping>
* 还有一些小坑，根据错误提示就能改好

### 下一篇文章再来分析一下项目代码吧
