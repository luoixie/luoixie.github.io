---
layout: post
title: markdown文件转为pdf文件
description: markdown输出为pdf文件

---

# markdown文件转为pdf文件

> 一直都是在用`markdown`作为写笔记的工具，喜欢`markdown`的排版简洁，上手速度快。
> 
> 毫无疑问，`Sublime Text`是一款好用的工具，不仅仅是编程，依赖于强大的插件库以及秒开的速度，我深深地迷上了。

[Sublime Text markdown 介绍](http://macplay.leanote.com/post/%E8%BF%91%E4%B9%8E%E5%AE%8C%E7%BE%8E%E7%9A%84-Markdown-%E5%86%99%E4%BD%9C%E4%BD%93%E9%AA%8C-Sublime-Text-3-OmniMarkupPreviewer)

最近想把`markdown`文件转为pdf,但google后也没有发现好的方法(免费的)，然后自己琢磨了一个方法。

思路是：markdown --> html --> pdf

使用工具：

    markdown文件：SublimeText 3 + OmniMarkupPreviewer

    html文件：利用OmniMarkupPreviewer直接可以输出 html文件

    pdf文件：利用chrome浏览器的打印功能，直接可以另存为pdf文件

似乎看起来没有什么难度，但实际还是有一些坑的。
    
        1.页面内容出现滚动条，在另存为pdf时，文件会不完整(只会保存当前页面的可见内容，滚动才能看的内容是不会输出的）。这时候可以给<pre>标签增加css样式，强制文本换行。

            pre{
                white-space: pre-wrap;
                word-wrap: break-word;
            }
        

        2.Firefox打印时一般是直接调用打印机的，但可以通过安装 福昕pdf阅读器，在打印的时候选择福昕pdf作为输出，就可以另存为pdf了；

        3.输出pdf之前记得把html的font-size值调整一下，不然转成pdf后你会哭的(输出的字体太小了)。

感觉这样的操作还是不够完美，要是`OmniMarkupPreviewer`集成输出pdf的功能就好了。



