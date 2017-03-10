---
title: CSS小知识
date: 3/10/2017 10:54:57 AM 
categories:
tags:
     - CSS
     - 小知识
---
##### 控制一句话长度超出隐藏显示省略号
*列如：* 
> .class{white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
> 
> > white-space：nowrap;表示文本不会换行，在同一行继续，知道遇到<br /\>标签为止；

> > overflow：hidden;不显示超过对象尺寸的内容，就是把超出的部分隐藏了；
> 
> > text-overflow：ellipsis;当文本对象溢出是显示...，当然也可是设置属性为clip不显示点点点；
>
<!--more-->

### 渐变背景的写法
> background: -webkit-gradient(linear,left top,left bottom,color-stop(0,#9E9E9E),color-stop(1,#d2c9b5));
*（颜色代码自定义即可）*
>
### null和undefined的区别
* null和undefined基本是同义的，只有一些细微的差别。
* null表示"没有对象"，即该处不应该有值。典型用法是：

> 作为函数的参数，表示该函数的参数不是对象。

> 作为对象原型链的终点。

*Object.getPrototypeOf(Object.prototype)// null*

* undefined表示"缺少值"，就是此处应该有一个值，但是还没有定义。典型用法是：
> 变量被声明了，但没有赋值时，就等于undefined。
> 调用函数时，应该提供的参数没有提供，该参数等于undefined。
> 对象没有赋值的属性，该属性的值为undefined。
> 函数没有返回值时，默认返回undefined。

### CSS3点跳动
	<style>
		dot {

		    display: inline-block; 
		    height: 1em; line-height: 1;
		    text-align: left;
		    vertical-align: -.25em;
		    overflow: hidden;
		    font-family: "微软雅黑";
		}
		dot::before {
		    display: block;
		    content: '...\A..\A.';
		    white-space: pre-wrap;
		    animation: dot 3s infinite step-start both;
		}
		@keyframes dot {
		    33% { transform: translateY(-2em); }
		    66% { transform: translateY(-1em); }
		}
	</style>
	<h1 style="font: 10rem/1.2 '楷体'; color: #e9ec09;">
		<dot>...</dot>
	</h1>