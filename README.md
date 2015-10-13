# icon-font-svn
icon font 使用与svn应用分享

##icon font 字体概述
css3增加了@font-face属性，传统的浏览器是通过font-family来设置字体，如果系统里没有的话就用其它字体来代替。
有了@font-face属性就方便多了，可以由开发人员通过设计自定义字体来进行的，加载过程是浏览器通过下载字体，再进行渲染页面
@font-face可以设置自定义自体，也可以设置自定义图片字体,font icon由此诞生。@font-face 引入生成好的字体文件 ，然后在网
页中需要使用某个图标的地方，写上对应的“文字”，那么在浏览器中就可以看到图标。
 [icon font](http://www.iconfont.cn/)  是国内第一家在线网络字体生成的工具网站，里面还有许多icon字体可以应用
 
 Iconfont 使用起来很简单，打开它的首页，你会发现很多图标，点击你需要的图标，就会发现图标到了右上角的购物车里，选择好
 了图标之后，点击购物车，即可下载下来一个 zip 包。

解压之后，会出现：demo.html, iconfont.eot, iconfont.svg, iconfont.ttf, iconfont.woff 这几个文件。

其中 demo.html 文件是使用说明和效果，另外四个就是为兼容各个平台而转换生成的字体文件。你只需要打开 demo.html 文件
就可以看到详细的使用说明。
使用字体图标有很多好处，大体如下：

>兼容性好，各个平台浏览器基本都可以使用，而且在某些低级浏览器中，效果比图片更好
　相对于同效果的图片相比，体积小，减少 http 请求，增加前端性能
　可维护性好，维护起来可以通过增减字体快速应用
　交互性好，改变字体颜色即可改变图标的颜色，同时可以配合 CSS3 的动画、渐变、过渡、变形等属性实现
　复杂的交互

 然也有一些缺点，例如图标通常只有一种颜色，虽然渐变可以使其颜色更加丰富，但是兼容性没了。还有一些其他的缺点，不过对于
 iconfont 这个工具来说，最大的缺点就是图标太少。国外网站iconfont字体有 [fontello](http://fontello.com/) 可以使用。



###PC端应用教程
 
 >font-face声明字体
 
```python
 
　@font-face {
　
　font-family: 'iconfont';
　
 src: url('iconfont.eot'); /* IE9*/
 
 src: url('iconfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */

 url('iconfont.woff') format('woff'), /* chrome、firefox */

 url('iconfont.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/

 url('iconfont.svg#iconfont') format('svg'); /* iOS 4.1- */

}
```
 
 >定义使用的iconfont样式
 
```python
　.iconfont{
　  font-family:"iconfont";
　　font-size:16px;font-style:normal;
　　-webkit-font-smoothing: antialiased; 抗锯齿显示样式，safair或chrome
　　-moz-osx-font-smoothing: grayscale;
　　display: block; 如果出现小方块，在ie7下，则加这句话
　　-webkit-text-stroke-width: 0.2px;  pc的chrome出现严重的锯齿
　　}
```
 >页面引用
```python
  <i class="iconfont">&#33</i>
```
###应用注意事项：
  
  >只在你确定你非常需要 @font-face的时候才使用他
  >将你的@font-face定义在所有的SCRIPT标签前
  >如果你有许多字体文件，考虑将它们分散到几个域名下。
  >不要包含没有使用的 @font-face声明——IE将不分它使用与否，通通加载
  >Gzip字体文件，同时给它们一个未来的过期头部声明
  >考虑字体文件的后加载，起码对于IE。
  
[参考网址](http://www.w3cfuns.com/article-1300-2.html)
[参考网址](http://www.cnblogs.com/demix/archive/2009/11/28/1612715.html)

###icon font制作 
     
把制作好的AI图,另存为svg, 然后通过[网址](http://www.iconfont.cn/icons/uploadShow)  上传, 点击加入购物车，然后在购物车中下载，会生成调用demo，进行对图片字段的调用。
  
以上是icon font 字体的使用，下面介绍svg的应用。
  
#SVG的应用

SVG可缩放矢量图形（Scalable Vector Graphics）是基于可扩展标记语言（XML），用于描述二维矢量图形的一种图形格式。
###特点

1．任意放缩。
     用户可以任意缩放图像显示，而不会破坏图像的清晰度、细节等。
2．文本独立。
     SVG图像中的文字独立于图像，文字保留可编辑和可搜寻的状态。也不会再有字体的限制，用户系统即使没有安装某一字   体，也会看到和他们制作时完全相同的画面。
3．较小文件。
     总体来讲，SVG文件比那些GIF和JPEG格式的文件要小很多，因而下载也很快。
4．超强显示效果
     SVG图像在屏幕上总是边缘清晰，它的清晰度适合任何屏幕分辨率和打印分辨率。
5．超级颜色控制。
    SVG图像提供一个1600万种颜色的调色板，支持ICC颜色描述文件标准、RGB、线X填充、渐变和蒙版。

###使用内联SVG

>SVG作为背景图片使用
>SVG作为src属性使用
>内联SVG

###声明一个SVG元素

```python
<svg xmlns="http://www.w3.org/2000/svg" width="400" height="300" viewBox="0 0 400 300">
 <!--  svg stuff here  -->
</svg>
```

###创建SVG图形

####circle:基础图形，基于中心点以及半径来创建的圆形。
对于circle元素，我们有3个需要指定的属性。它们是cx，cy，r。cx和cy是圆心在X轴和Y轴上的坐标，如果没有指定的话，它们的默认值为0。r为圆形的半径。一般来说，对一个圆形元素来说我们可以看到如下的标签：

```python
<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100">
  <circle cx="50" cy="50" r="50"></circle>
</svg>
```

####rect:基础图形，基于角的位置和矩形的宽度和高度来创建的矩形。

矩形的创建跟圆形的创建方式差不多。就它最基础的形式来说，我们需要为其指定左上角的的坐标x和y，以及该矩形的宽度width和高度height的值。其标签如下所示：

```python
<svg xmlns="http://www.w3.org/2000/svg" width="200" height="100" viewBox="0 0 200 100">
  <rect x="0" y="0" width="200" height="100"></rect>
</svg>
```
####polygon:基础图形，基于坐标点和两点相连而成的直线线段来创建的多边形。

我们可以通过在points属性上的多组 x-y 坐标点来定义我们的多边形元素。这些坐标点通过直线线段来连接。标签声明如下：

```python
<svg xmlns="http://www.w3.org/2000/svg" width="200" height="200" viewBox="0 0 200 100">
  <polygon points="0,50 50,0 150,0 200,50 150,100 50,100"></polygon>
</svg>
```
####path:万能的图形，可以用来创建任意的形状。所有基础图形都能由它来创建。
path元素是在形状处理方面最强大的元素。在path元素中，我们可以定义d属性，这个属性为我们的路径如何延伸作出了定义。d属性可以让我们通过一系列的命令来指定一个运动轨迹。我们可以用直线命令和弯曲命令来构建一些复杂的形状。但实际上，你并不希望手写贝塞尔曲线这种玩意，二是通过矢量软件来创建并输出SVG。但了解一下他们并不是什么坏事。

M x y:移动到坐标x-y
L x y:从当前位置画一条直线到坐标x—y
H x:从当前位置画一条水平线到坐标x
V y:从当前位置画一条垂直线到坐标y
Z:闭合路径

```python
<svg xmlns="http://www.w3.org/2000/svg" width="200" height="200" viewBox="0 0 200 200">
  <path d="M 0 0 H 200 V 200 H 0 Z"></path>
</svg>
```

fill:元素的填充颜色
fill-opacity:元素的填充颜色透明度
stroke:元素的笔画颜色
stroke-width:元素的笔画宽度
stroke-opacity:元素的笔画颜色透明度

```python
<svg xmlns="http://www.w3.org/2000/svg" width="200" height="200" viewBox="0 0 200 200">
  <circle class="circle" cx="100" cy="100" r="90" fill="#3399cc" stroke="#333333" stroke-width="5"></circle>
</svg>

.circle {
  transition: stroke 0.3s, fill 0.3s;
}

.circle:hover {
  stroke: #3399cc;
  fill: #333333;
}
```





  
  
  
  
  
  
 
 
 
 








