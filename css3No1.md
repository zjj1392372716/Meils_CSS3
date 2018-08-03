**圆角**

```css
border-radius: 5px 4px 3px 2px; 
/* 四个半径值分别是左上角、右上角、右下角和左下角，顺时针 */ 

border-radius:10px; 
/* 所有角都使用半径为10px的圆角 */ 

/* 实心圆 */
div{
    height:100px;/*与width设置一致*/
    width:100px;
    background:#9da;
    border-radius:50px;/*四个圆角值都设置为宽度或高度值的一半*/
}

/* 左半圆 */
div.semi-circle{ 
    height:100px;
    width:50px;
    background:#9da;
    border-radius:50px 0 0 50px;
}
```

**阴影 box-shadow**

![](http://img.mukewang.com/54292d620001ffb107080250.jpg)

```css
box-shadow: X轴偏移量 Y轴偏移量 [阴影模糊半径] [阴影扩展半径] [阴影颜色] [投影方式];

.box_shadow{
  box-shadow:4px 2px 6px #333333; 
}

.box_shadow{
  box-shadow:4px 2px 6px #333333 inset; 
}

1、阴影模糊半径与阴影扩展半径的区别

 - 阴影模糊半径：此参数可选，其值-只能是为正值-，如果其值为0时，表示阴影不具有模糊效果，其值越大阴影的边缘就越模糊；

 - 阴影扩展半径：此参数可选，其值-可以是正负值-，如果值为正，则整个阴影都延展扩大，反之值为负值时，则缩小；

```

**图片边框 border-image**

```css
#border-image{
   background:#F4FFFA;
   width:210px; height:210px; border:70px solid #ddd;
   border-image:url(borderimg.png) 70 repeat  
}
```
![](http://img.mukewang.com/52e220780001091a03530354.jpg)

```css
#border-image {
     width:170px;
     height:170px;
     border:70px solid;
     border-image:url(borderimg.png) 70 round;
 }
```

![](http://img.mukewang.com/52e2216700014c4103190312.jpg)

```css
border-image:url(borderimg.png) 70 stretch
```

![](http://img.mukewang.com/52e2218d0001d45403530366.jpg)



**渐变 gradient**

```css
// 线性渐变
background: linear-gradient(to bottom , orange, yellow);

第一个参数： 
/* to bottom   往下
   to bottom right  左下到右下
   to bottom left
   to up left
   to up
   to up right
   to right
   to left
*/

第二个参数： 起始颜色
第三个参数： 终止颜色
```

```css
background: linear-gradient(30deg, red, green);

// 可以指定角度，0度为 to up ， 随着度数的增加，是顺时针旋转
```

```css
// 可以设置开始渐变和结束渐变的位置

background: linear-gradient(to bottom, orange 10% , blank 70%);

// 从高度的10%位置开始渐变，到高度的 70%停止渐变
```
```css
// 放射性渐变
background： radial-gradient(circle at center top , orange, blank);

// 第一个参数 circle | ellipse 圆形 | 椭圆形

// 第二个参数 用at 关键之指定 渐变的起点位置
/**
    center center
    center top  顶部
    center right
    center left
    left top 左上角
    right top
    center bottom 
    bottom left
    botttom right
    ...

    [也可以是像素单位 如：130px 50px]
*/
```

```css
// 指定渐变范围
background： linear-gradient (circle closest-side at center top, orange, blank); 


/**
    closest-side    可渐变到离着最近的边
    farthest-side   可渐变到离着最远的边
    closest-corner  可渐变到离着最近的角
    fathest-corner  可渐变到离着最远的角
**/
```

```
// 兼容写法

    background-image: -ms-linear-gradient(top, #fff, #dededc);
    background-image: -moz-linear-gradient(top, #fff, #dededc);
    background-image: -webkit-gradient(linear, left top, left bottom, from(#fff), to(#dededc));
    background-image: -webkit-linear-gradient(top, #fff, #dededc);
    background-image: -o-linear-gradient(top, #fff, #dededc);
    background-image: linear-gradient(top, #fff, #dededc);

```

**文本阴影**

```css
text-shadow: X-Offset Y-Offset blur color;

X-Offset：表示阴影的水平偏移距离，其值为正值时阴影向右偏移，反之向左偏移；      

Y-Offset：是指阴影的垂直偏移距离，如果其值是正值时，阴影向下偏移，反之向上偏移；

Blur：是指阴影的模糊程度，其值不能是负值，如果值越大，阴影越模糊，反之阴影越清晰，如果不需要阴影模糊可以将Blur值设置为0；

Color：是指阴影的颜色，其可以使用rgba色。


```

**文本自动换行**

文本换行其实是个非常常用但并不起眼的特性。你什么都不用设，浏览器自动就会换行。例如英语，浏览器会根据容器尺寸，选择在半角空格或连字符处换行。例如中文，浏览器会选择在文字或标点符号处换行。但有时遇到长单词或URL浏览器就没这么智能了，会出现撑破容器的现象，很难看，如下图

![](https://segmentfault.com/img/bVG3nq?w=561&h=90)

容器定宽150px的前提下，普通文字如左图浏览器足以胜任自动换行，右图遇见长单词或URL，浏览器就力不从心了。当然，你能为容器设置overflow:auto;，让滚动条出现，以避免撑破容器。或干脆overflow:hidden;让超出部分隐藏，见下图

![](https://segmentfault.com/img/bVG3ns?w=333&h=105)



> 1、word-wrap 【 overflow-wrap 】  实现断词换行

> 效果如下：(可以解决长单词和url不能换行的问题了)

![](https://segmentfault.com/img/bVG3nu?w=179&h=140)

```css
word-wrap：normal | break-word
/*
normal：    允许内容顶开或溢出指定的容器边界。
break-word：内容将在边界内换行。如果需要，单词内部允许断行。

***** CSS3中将 <' word-wrap '> 改名为 <' overflow-wrap '>；
*/


.test p{
    width:100px;
    border:1px solid #000;
    background-color:#eee;
}
.normal p{
    word-wrap:normal;
    overflow-wrap:normal;
}
.break-word p{
    word-wrap:break-word;
    overflow-wrap:break-word;
}
```

> 2、word-break     设置浏览器自动换行的方式

![](https://segmentfault.com/img/bVG3nz?w=355&h=143)


```
word-break：normal | keep-all | break-all

*******常用 break-all，break-all显得比较整洁

word-wrap的normal是沿用浏览器默认的换行方式
keep-all 是不换行
word-break的break-all是改变浏览器默认的换行方式，让浏览器无视半角空格，直接根据容器尺寸换行
```

> 3、white-space   设置空白符和换行符

```
white-space：normal | pre | nowrap | pre-wrap | pre-line


****** 常用nowrap，不管你有多少，强制让其一行显示，然后隐藏超出的部分

normal：
默认处理方式。
pre：
用等宽字体显示预先格式化的文本，不合并文字间的空白距离，当文字超出边界时不换行。可查阅pre对象
nowrap：
强制在同一行内显示所有文本，合并文本间的多余空白，直到文本结束或者遭遇br对象。
pre-wrap：
用等宽字体显示预先格式化的文本，不合并文字间的空白距离，当文字碰到边界时发生换行。
pre-line：
保持文本的换行，不保留文字间的空白距离，当文字碰到边界时发生换行。
```

> 4、word-spacing   单词间隔

> 5、letter-spacing  字符的间隔

> 6、text-overflow   文本溢出处理

![](http://img.mukewang.com/53070cc00001a5bc06000200.jpg)

```
text-overflow:ellipsis; 
```

> 实例 ： 文字溢出时显示为省略号。

```css
div{
    width: 100px;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
}
```

-----------

**服务器字体**

```css
// 以 FontAwesome 图标字体库
@font-face{
    font-family: 'FontAwesome'; // 字体名
    src: url('../fonts/fontawesome-webfont.eot?v=4.7.0');
    src: url('../fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'),
        url('../fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'),
        url('../fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'),
        url('../fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'),
        url('../fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
    font-weight: normal;
    font-style: normal;
}

src 引入字体文件，format属性声明字体格式。每种字体格式对应不同的后缀名

// 使用字体
.fa {
    font: normal normal normal 14px/1 FontAwesome;
}
```

```
font-style: italic; 斜体 
```

**背景起始位置 background-origin**

* 如果背景不是`no-repeat`，这个属性无效，它会从边框开始显示。

```css
background-origin : border-box | padding-box | content-box;

// 内边距（默认值）
```

![](http://img.mukewang.com/531003de0001166903660166.jpg)


**背景裁剪 background-clip**

```css
// 
background-clip ： border-box | padding-box | content-box | no-clip

/*
    参数分别表示     从边框、或内填充，或者内容区域向外裁剪背景。
    no-clip         表示不裁切，和参数border-box显示同样的效果。
    backgroud-clip  默认值为border-box。
*/
```

![](http://img.mukewang.com/5310065d0001c95103660166.jpg)

**背景大小 background-size**

```css
background-size: auto | <长度值> | <百分比> | cover | contain

1、auto: 默认值，不改变背景图片的原始高度和宽度；

2、<长度值>: 成对出现如【200px 50px】，将背景图片宽高依次设置为前面两个值，当设置一个值时，将其作为图片宽度值来等比缩放；

3、<百分比>：0％~100％之间的任何值，将背景图片宽高依次设置为所在元素【宽高乘以前面百分比得出的数值】，当设置一个值时同上；

4、cover：顾名思义为覆盖，即将背景图片【等比缩放】以【填满整个容器】；

5、contain：容纳，即将背景图片 【等比缩放】至某一边紧贴容器边缘为止。
```

```css
// 不调整尺寸，调整边距
background-image: url(/i/eg_bg_03.gif);
background-repeat: space;
```
![]()

```css
// 调整尺寸，不调整边距，满填充
background-image: url(/i/eg_bg_03.gif);
background-repeat: round;
```

![]()

**背景图片 background-image**

```css
// 多背景图片3
background-image: url(flower.png), url('flower-green.png'), url('sky.png');

background-repeat: no-repeat, repeat-x, no-repeat;
background-position: 3% 98%, 85%, center center, top;


.demo{
    width: 300px;
    height: 140px;
    border: 1px solid #999;
    background-image: url(http://img.mukewang.com/54cf2365000140e600740095.jpg),
                      url(http://img.mukewang.com/54cf238a0001728d00740095.jpg),
                      url(http://img.mukewang.com/54cf23b 60001fd9700740096.jpg);
    background-position: left top, 100px 0, 200px 0;
    background-repeat: no-repeat, no-repeat, no-repeat;
    margin:0 0 20px 0;
}
```