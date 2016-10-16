---
layout: post
title: css3动画属性animation
description: css3里引入了一个新的动画属性animation,结合@keyframes可以做出各种的动画效果，可惜的是IE10以下是不支持的。
---

# CSS3动画属性 animation

#### 浏览器支持情况

属性 | chrome | IE | FireFox | Safari | Opera
---|---|---|---|---|---
animation | 43.0 /4.0 -webkit- | 10.0 | 16.0 /5.0 -moz-  | 9.0 /4.0-webkit-  | 30.0 /15.0 -webkit- /12.0 -o-

#### animation默认参数

`animation`:name duration timing-function delay iteration-count direction fill-mode play-state;

[各参数](http://www.runoob.com/cssref/css3-pr-animation.html)

属性 | 含义
---|---
`animation-name` | 指定要绑定到选择器的关键帧的名称(执行动画的名称)
`animation-duration` | 动画指定需要多少秒或毫秒完成;默认为0
`animation-timing-function`|设置动画将如何完成一个周期；默认为ease(动画以低速开始，然后加快，在结束前变慢。),ease-out(低速结束)
`animation-delay`|动画启动前的延时间隔；默认为0 ，等待2s;提前2S:-2s
`animation-iteration-count`|定义动画的播放次数； infinite：无限次播放
`animation-direction`| 指定是否应该轮流反向播放动画。方向播放：reverse
`animation-fill-mode`|规定当动画不播放时（当动画完成时，或当动画有一个延迟未开始播放时），要应用到元素的样式
`animation-play-state`|指定动画是否正在运行或已暂停。paused / running
`initial`|设置属性为其默认值；
`inherit`|从父元素集成属性；

<hr/>
### @keyframes

> 同样也可以使用 #keyframes 来创建动画
> 
> 可以通过各个百分比的具体参数来设定动画每一帧的变化，或者是直接用from to

#### @keyframes 语法

> @keyframes animationname {keyframes-selector {css-styles;}}

值 | 说明
---|---
`animation-name` | 必需的。定义动画的名称
`keyframes-selector` | 定义动画的名称
`animation-name` | 必需的，动画持续时间的百分比。<br>合法值：<br>from (和0%相同)<br>to (和100%相同)<br>注意： 您可以用一个动画keyframes-selectors。
`css-styles` | 必需的。一个或多个合法的CSS样式属性

#### demo 

> 结合 animation 和 @keyframes

```html
    //html
    <div id="circle"></div>

    //css
    #circle{
        width:50px;
        height:50px;
        border-radius:25px;
        background-color:red;
        -webkit-border-radius:25px;
        -moz-border-radius:25px;
        -o-border-radius:25px;
        position:relative;
        animation:move 5s infinite ease-out;
        -moz-animation:move 5s infinite ease-out; /* Firefox */
        -webkit-animation:move 5s infinite ease-out; /* Safari and Chrome */
        -o-animation:move 5s infinite ease-out; /* Opera */
    }
    @keyframes move{
        from {top:50px; left:0;}
        to {top:50px;left:300px;}
    }
    @-webkit-keyframes move{
        from {top:50px; left:0;}
        to {top:50px;left:300px;}
    }
    @-moz-keyframes move{
        from {top:50px; left:0;}
        to {top:50px;left:300px;}
    }
    @-o-keyframes move{
        from {top:50px; left:0;}
        to {top:50px;left:300px;}
    }
```

[测试demo](http://codepen.io/luoixie/pen/yaxgBx)

<hr/>