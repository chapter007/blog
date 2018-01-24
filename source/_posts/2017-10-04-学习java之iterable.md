---
layout: content
title: 学习java之iterable
---

# 学习java之iterable
##一些废话
十一废了几天以后有点良心不安，打开spark组的任务，看到里面有iterable的学习计划。emm，我的java学的很不扎实，只会一些基础语法，乘此机会，学习一下吧
## 学习iterable和iterator
从语法上来看iterable是可以迭代的意思，而iterator是迭代者，也就是迭代器的意思。
### iterator
iterator是提供迭代机制的对象，具体如何迭代都是iterator接口规范的
它包含三个方法：hasNext,next,remove.remove用到的比较少
* 每次迭代前，先调用hasNext()探测是否迭代到终点。
* next方法不仅要返回当前元素，还要后移游标cursor
* remove方法用来删除最近一次迭代出的元素
* 迭代出的元素是原集合中元素的拷贝（重要）
* 需要配合foreach使用
迭代的细节，需要理解的：
* hasNext,next,remove的调用顺序
* 迭代出的元素是原集合中元素的拷贝（重要）
### 手动迭代的例子，与foreach的原理一样
	public static void main(String[] args)
	{

			List<Integer> li = new ArrayList<>();
			
			li.add(1);
			li.add(2);
			li.add(3);
			
			//不使用foreach 而手动迭代
			Iterator<Integer> iter = li.iterator();    //获取ArrayList 的迭代器
			
			while(iter.hasNext())                      //①先探测能否继续迭代
			{
				System.out.println(iter.next());       //②后取出本次迭代出的元素
			 
				//invoke  remove()                     //③最后如果需要，调用remove
				  
			}
		  
	}
### iterable
一个集合如果要表明自己可以迭代，可以使用foreach语句，就必须实现iterable接口，表示自己是可以迭代的，要实现iterable接口，需要为foreach语句提供一个迭代器。这个迭代器是用接口定义的iterator方法提供的。iterator方法需要返回一个iterator对象

### 迭代出来的元素都是原来集合元素的拷贝
Java集合中保存的元素实质是对象的引用(可以理解为C中的指针)，而非对象本身。

迭代出的元素也就都是 引用的拷贝，结果还是引用。那么，如果集合中保存的元素是可变类型的，我们就可以通过迭代出的元素修改原集合中的对象。

而对于不可变类型，如String  基本元素的包装类型Integer 都是则不会反应到原集合中。

## 小实验，让自己的类支持迭代
	public class Main
	{

		public static void main(String[] args)
		{


			MyString s = new MyString("1234567");
			
			
			for(char c:s)
			{
				System.out.println(c);
			}

			

		}

	}




	class MyString implements Iterable<Character>
	{
		
		private int length = 0;
		private String ineers = null;
		
		public MyString(String s)
		{
			this.ineers = s;
			this.length = s.length();
			
		}
		
		
		@Override
		public Iterator<Character> iterator()
		{
			
			
			class iter  implements Iterator<Character>     //方法内部类
			{
				private int cur= 0;
				
				
				@Override
				public boolean hasNext()
				{
					return cur != length;
				}

				@Override
				public Character next()
				{
					
					Character c = ineers.charAt(cur);
					cur++;
					return c;
				}
				
				public void remove()
				{
					 // do nothing 
					
				}

			}
			return new iter();     //安装Iterable接口的约定，返回迭代器
					   
		}
		
	}