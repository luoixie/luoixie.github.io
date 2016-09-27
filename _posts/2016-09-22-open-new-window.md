---
layout: post
title: html页面跳转新窗口
description: html页面跳转新窗口的方法
---
#  HTML跳转新窗口的方法
- 笔试遇到这样的一个问题，特意整理一下。

#### 方法一  纯HTML
``` html
	<a href="http://www.cnblogs.com" target="_blank">博客园</a>
```

#### 方法二 使用 `onclick`
``` javascript
	// HTML 
	<a onclick="openUrl('http://www.cnblogs.com')">博客园</a>
	// js
	// 使用 'window.open()'
	<script type="text/javascript">
		function openUrl(url){
			window.open(url);
		}
	</script>
```	
- 下面用到的 `openUrl()`都是用法二的函数
- [window.open()](http://www.w3school.com.cn/jsref/met_win_open.asp) 的具体用法

#### 方法三 使用 `href="javascript:openUrl()"`
``` html
	// HTML
	<a href="javascript:openUrl('http://www.cnblogs.com')">博客园</a>
```

#### 方法四 直接使用 `window.open()`
``` html
	<a onclick="window.open('http://www.cnblogs.com')">博客园</a>
```

#### 方法五 使用 `id + onclick`
``` javascript
	// HTML
	<p id="btn">博客园</p>
	// js
	<script type="text/javascript">
		var btn = document.getElementById('btn');
		btn.onclick =function(){
			openUrl("http://www.cnblogs.com");
		};
	</script>
```

#### 方法六 使用 `addEventListener()`
``` javascript
	// HTML
	<p id="btn">博客园</p>
	// js
	<script type="text/javascript">
		var btn = document.getElementById('btn');
		btn.addEventListener("click", function(e){
 			openUrl("http://www.cnblogs.com");
 		}, false);
	</script>
```