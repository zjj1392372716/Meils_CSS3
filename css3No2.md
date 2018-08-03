### css3 2D变形处理

#### 旋转

```
transform: rotate(20deg);
-webkit-transform: rotate(20deg);
 -moz-transform: rotate(20deg);
```

#### 缩放

```
transform: scale(0.7);
-webkit-transform: scale(0.7);
 -moz-transform: scale(0.7);
```

```
transform: scale(0.7, 0.5);
// 水平 0.7 垂直 0.5
```


#### 平移

```
transform: translate(20px, 50px);
// 水平向右 20px
// 垂直向下 50px
```


#### 倾斜

```
transform: skew(20deg, 30deg);
// 水平倾斜 20deg， 垂直倾斜 30deg

```

#### 混合

```
// 先旋转、再缩放、再移动
transform: rotate(45deg) , scale(0.5), translate(20px , 40px);
```

> 案例： 

```html
<!DOCTYPE html>
<html>
<head>
<style> 
body
{
    margin:30px;
    background-color:#E9E9E9;
}

div.polaroid
{
    width:294px;
    padding:10px 10px 20px 10px;
    border:1px solid #BFBFBF;
    background-color:white;
    /* Add box-shadow */
    box-shadow:2px 2px 3px #aaaaaa;
}

div.rotate_left
{
    float:left;
    -ms-transform:rotate(7deg); /* IE 9 */
    -moz-transform:rotate(7deg); /* Firefox */
    -webkit-transform:rotate(7deg); /* Safari and Chrome */
    -o-transform:rotate(7deg); /* Opera */
    transform:rotate(7deg);
}

div.rotate_right
{
    float:left;
    -ms-transform:rotate(-8deg); /* IE 9 */
    -moz-transform:rotate(-8deg); /* Firefox */
    -webkit-transform:rotate(-8deg); /* Safari and Chrome */
    -o-transform:rotate(-8deg); /* Opera */
    transform:rotate(-8deg);
}
</style>
</head>
<body>

<div class="polaroid rotate_left">
    <img src="/i/ballade_dream.jpg" alt="郁金香" width="284" height="213" />
    <p class="caption">上海鲜花港的郁金香，花名：Ballade Dream。</p>
</div>

<div class="polaroid rotate_right">
    <img src="/i/china_pavilion.jpg" alt="世博中国馆" width="284" height="213" />
    <p class="caption">2010年上海世博会，中国馆。</p>
</div>
</body>
</html>

```


#### transform-origin 定义变形的基准点

![](http://img.mukewang.com/53391ea500013e4706860384.jpg)

```
transform-origin: x-axis y-axis z-axis;
x-axis	
定义视图被置于 X 轴的何处。可能的值：
left
center
right
length
%

y-axis	
定义视图被置于 Y 轴的何处。可能的值：
top
center
bottom
length
%

z-axis	
定义视图被置于 Z 轴的何处。可能的值：
length

.wrapper {
  width: 400px;
  height: 100px;
  border: 2px dotted red;
  margin: 20px auto; 
  text-align: center;
  line-height: 100px;
}
.wrapper div {
  background: orange;
  color: #fff;
  -webkit-transform: skew(15deg);
  -moz-transform: skew(15deg);
  transform: skew(15deg);
  -webkit-transform-origin: top right;
  -moz-transform-origin: top right;
  transform-origin: top right;
}
```

-----------------

### css3 3D变形处理

> css3 3D坐标系

![](https://images2015.cnblogs.com/blog/1105033/201705/1105033-20170506092034507-1009808768.png)


#### rotateX, rotateY, rotateZ

![]()

```css
transform: rotateX(10deg);
```