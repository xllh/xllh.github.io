---
layout: post
title: MarkDown完整语法-中文版
description: "MarkDown语法 中文"
category: "工具"
tags: ["MarkDown"]
--- 
##官方语法文档
[MarkDown官方语法-英文](http://daringfireball.net/projects/markdown/syntax)

-------------------
###哲学

MarkDown追求**易读**和**易写**。

MarkDown格式化的文档应该是纯文本，可以原样打印的。Markdown语法的最大灵感来自纯文本邮件的格式。

MarkDown语法中的标点符号基本都是语义化的，易于记忆。

###内嵌HTML

MarkDown语法其中一个目的就是：用于书写网页。

MarkDown语法支持的HTML语法不全面，只支持那些可以在纯文本中体现的元素。（博主：例如html的a标签中target="*"属性，MarkDown就不支持。）

对于MarkDown不支持的HTML元素或属性，可以直接使用HTML标签。**但是块级别的HTML元素前后都需要添加一空行，并且开始和结束标签不能缩进！这样MarkDown就会自动忽略该块级元素，所以块级别的元素中间的MarkDown元素不会被解析**。MarkDown支持span级别的HTML元素嵌入，任何位置，支持混写。

###自动转义特殊字符

MarkDown会将

* AT&T 自动转换成 AT&amp;T
* 4 < 5 自动转换成 4 &lt; 5
* &copy; 自动保留

###块元素

####段落和换行

每段落之间需要隔一空行。

段内换行 br 元素

####头

<p>一级标题<br />========</p>
<p>二级标题<br />--------</p>

<p>#一级标题<br />##二级标题<br />.<br />.<br />######六级标题<br /></p>

####文字引用
支持嵌套引用,支持嵌入其他语法
<div>
<p>>####毛主席教育我们</p>
<p>></p>
<p>>>好好学习，</p>
<p>>天天向上。</p>
<p>></p>
<p>>* 我们要学习</p>
<p>>* 并坚持不懈</p>
</div>

------------------
示例：
>####毛主席教育我们
>
>>好好学习，
>天天向上。
>
>* 我们要学习
>* 并坚持不懈

------------------

####列表

无序列表

<div>
<p>* 红</p>
<p>* 绿</p>
<p>* 蓝</p>
</div>
------------------
示例：

* 红
* 绿
* 蓝

------------------
有序列表

<div>
<p>1. 把冰箱门儿打开</p>
<p>2. 把大象装冰箱</p>
<p>3. 把冰箱门儿带上</p>
</div>

------------------
示例：

1. 把冰箱门儿打开
2. 把大象装冰箱
3. 把冰箱门儿带上

------------------

列表中添加引用，引用需要缩进。

如下情况:

<p>1986. What a great season.</p>

<p>1986\. What a great season.</p>

####代码块

代码缩进四个空格或者一个Tab，转成HTML时，对应代码会被包含到pre和code标签中。
<code>
    <pre><code></code></pre>
</code>

<div>
<p>Java代码</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;public static void main(String[] args){</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;System.out.println("Hello MarkDown.");</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;}</p>
</div>

Java代码

    public static void main(String[] args){
        System.out.println("Hello MarkDown.");
    }


####水平线

都可以转换成一个hr元素

<div>
    <p>* * *</p>
    <p>***</p>
    <p>*****</p>
    <p>- - -</p>
    <p>-------------------------------------</p>
</div>

###SPAN元素

####链接

1. 行内链接

<div>
    <p>[百度链接](http://baidu.com/ "百度一下")</p>
</div>

2. 引用链接

<div>
    <p>[百度链接][baidu]</p>
    <p>[baidu]:http://baidu.com/ "百度一下"</p>
</div>

关键字baidu，大小写不敏感。

####强调

星号*和下划线_的在这里完全相同。

<div>
    <p>*这会被em元素包裹*</p>
    <p>_这会被em元素包裹_</p>
    <p>**这会被strong元素包裹**</p>
    <p>__这会被strong元素包裹__</p>
</div>

####代码

使用反引号。

<div>
    <p>Java函数 `printf()` 使用</p>
</div>

如果代码中包含反引号，则使用双反引号引用。内部反引号开头或结尾，需要空格。

<div>
    <p>``Java函数 `printf() 使用``</p>
    <p>`` `<printf()>` ``</p>
</div>

####图片

显然，定义一个图片的语义化符号很难。

行内定义

<div>
    <p>![Linux图片](/img/linux.gif "这是一张图片！")</p>
</div>

示例：

![Linux图片](/img/linux.gif "这是一张图片！") 

引用定义

<div>
    <p>![Linux图片][Linux]</p>
    <p>[linux]: /img/linux.gif "这是一张图片！"</p>
</div>

示例：

 ![Linux图片][Linux]
 
 [linux]: /img/linux.gif "这是一张图片！"
 
 **这里无法定义图片的尺寸！**如果需要使用html的img元素直接定义。


###杂项

####自动链接

<div>
    <p><http://www.baidu.com/></p>
    <p><adouteam@gmail.com></p>
</div>

示例：

<http://www.baidu.com/>

<buxianglongoschina@gmail.com>

####反斜杠转义'\'

可以转义的字符：

反斜杠：\\

反引号：\`

星号：\*

下划线：\_

大括号：\{\}

中括号：\[\]

小括号：\(\)

井号：\#

加号：\+

减号（连字符）：\-

小数点：\.

叹号：\!




 
 







