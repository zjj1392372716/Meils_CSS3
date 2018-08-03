### css3动画

#### transitions 动画

```css
// 动画效果1
// 鼠标移上去宽度变宽
div {
  width: 200px;
  height: 200px;
  background: red;
  margin: 20px auto;
  /* 指定过渡的css属性 */
  -webkit-transition-property: width;
  transition-property: width;
  /* 完成过渡所需的时间 */
  -webkit-transition-duration:.5s;
  transition-duration:.5s;
  /* 指定过渡函数 */
  -webkit-transition-timing-function: ease-in;
  transition-timing-function: ease-in;
  /* 开始出现的延迟时间 */
  -webkit-transition-delay: .18s;
  transition-delay:.18s;
}
div:hover {
  width: 400px;
  // 属性变化的时候出发过渡
}
```

`transition-property`用来指定过渡动画的CSS属性名称，而这个过渡属性只有具备一个中点值的属性（需要产生动画的属性）才能具备过渡效果，其对应具有过渡的CSS属性主要有：


![](http://img.mukewang.com/5344eca300010a8005510421.jpg)

`transition-timing-function` “缓动函数”。主要用来指定浏览器的过渡速度，以及过渡期间的操作进展情况，其中要包括以下几种函数：

![](http://img.mukewang.com/5344f1320001481905640812.jpg)

```
ease     慢 - 快 - 慢
linear   匀速
ease-in  慢 - 快
ease-out 快 - 慢
ease-in-out 快 - 慢 - 快
```

```
// 合并起来

a{ transition: background 0.8s ease-in 0.3,color 0.6s ease-out 0.3;}
```

> transitions 动画的一个缺点就是，只能指定开始和结束的属性值，然后在这个过程中实现对属性的平滑过渡，不能实现更为复杂的效果。


#### Animations 动画

```css
@keyframes changecolor{
  0%{
    background: red;
  }
  20%{
    background:blue;
  }
  40%{
    background:orange;
  }
  60%{
    background:green;
  }
  80%{
    background:yellow;
  }
  100%{
    background: red;
  }
}
div {
  width: 300px;
  height: 200px;
  background: red;
  color:#fff;
  margin: 20px auto;
}
div:hover {
  animation: changecolor 5s ease-out .2s;
}
```

`animation-name`: none | '...'   调用 @keyframes 定义好的动画

`animation-duration`: 主要用来设置CSS3动画播放时间

`animation-timing-function`: 属性主要用来设置动画播放方式。

```
具有以下几种变换方式：ease,ease-in,ease-in-out,ease-out,linear 和 cubic-bezier。
```

`animation-delay` : 属性用来定义动画开始播放的时间，用来触发动画播放的时间点。

`animation-iteration-count`: 属性主要用来定义动画的播放次数

`animation-iteration-count`: 属性主要用来定义动画的播放次数。

```css
animation-iteration-count: infinite | <number> 
```

`animation-direction`: 属性主要用来设置动画播放方向，其语法规则如下：

`animation-direction：`: 属性主要用来设置动画播放方向，其语法规则如下

```
其主要有两个值：normal、alternate
1、normal是默认值，如果设置为normal时，动画的每次循环都是向前播放；

2、另一个值是alternate，他的作用是，动画播放在第偶数次向前播放，第奇数次向反方向播放。
```

`animation-play-state`: 属性主要用来控制元素动画的播放状态。 [running和paused。]

`animation-fill-mode`: 属性定义在动画开始之前和结束之后发生的操作。主要具有四个属性值：none、forwards、backwords和both。其四个属性值对应效果如下：


none      默认值，表示动画将按预期进行和结束，在动画完成其最后一帧时，动画会反转到初始帧处

forwards  表示动画在结束后继续应用最后的关键帧的位置

backwards 会在向元素应用动画样式时迅速应用动画的初始帧

both      元素动画同时具有forwards和backwards效果