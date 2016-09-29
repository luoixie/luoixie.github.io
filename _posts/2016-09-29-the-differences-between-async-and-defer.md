---
layout: post
title: defer和async的区别
description: defer和async都是属于<script>元素
---

# defer 和 async 的区别

### `defer` 延迟脚本
> HTML 4.01中定义了`defer`属性,只适用于外部脚本;
> 
> 使用了 `defer` 属性的外部js文件，会和HTML并行加载，但脚本会延迟到整个页面解析完毕后才执行;
> 
> 尽管HTML5规范要求使用了 `defer`属性的外部脚本文件会按顺序执行，但由于浏览器的问题，延迟脚本不一定会按照顺序执行。

#### `defer`用法
```js
//在 <head>标签中使用
<script src="example.js" defer></script>
```

<hr/>

### `async` 异步脚本
> HTML5 中定义了 `async`属性,只适用于外部脚本;
> 
> 使用了 `async` 属性的外部脚本文件，会和HTML并行加载，加载完后立即执行文件;这时HTML的页面的解析会暂停，直至当前脚本执行完毕;
> 
> 同时有多个定义了`async`的脚本加载时，按照哪个脚本先加载完成就先执行哪个。

#### `async` 用法
```js
<script src="example1.js" async></script>
<script src="example1.js" async></script>
```

<hr/>

想详细了解 `defer` 和 `async` 的具体应用效果，可以看以下这些文章：

[浅谈script标签的defer和async](https://segmentfault.com/a/1190000006778717)

[script的defer和async](http://ued.ctrip.com/blog/script-defer-and-async.html#)

[async vs defer attributes](http://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html)

<hr/>
