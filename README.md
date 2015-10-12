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
 iconfont 这个工具来说，最大的缺点就是图标太少。国外网站iconfont字体有 [fontello](http://fontello.com/)
 
 
 ##PC端应用教程
 
 －font-face声明字体
 ``` python
 
　@font-face {font-family: 'iconfont';
　
 src: url('iconfont.eot'); /* IE9*/
 
 src: url('iconfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */

 url('iconfont.woff') format('woff'), /* chrome、firefox */

 url('iconfont.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/

 url('iconfont.svg#iconfont') format('svg'); /* iOS 4.1- */

}
```
 
 －定义使用iconfont的样式
 
 ``` python
　.iconfont{
　  font-family:"iconfont";
　　font-size:16px;font-style:normal;
　　-webkit-font-smoothing: antialiased; 抗锯齿显示样式，safair或chrome
　　-moz-osx-font-smoothing: grayscale;
　　display: block; 如果出现小方块，在ie7下，则加这句话
　　-webkit-text-stroke-width: 0.2px;  pc的chrome出现严重的锯齿
　　}
  ```
  
  
  -页面引用
  
  ``` python
  <i class="iconfont">&#33</i>
  ```
  应用注意事项：
  
  -只在你确定你非常需要 @font-face的时候才使用他
  -将你的@font-face定义在所有的SCRIPT标签前
  -如果你有许多字体文件，考虑将它们分散到几个域名下。
  -不要包含没有使用的 @font-face声明——IE将不分它使用与否，通通加载
  -Gzip字体文件，同时给它们一个未来的过期头部声明
  -考虑字体文件的后加载，起码对于IE。
  
        [参考网址](http://www.w3cfuns.com/article-1300-2.html)
        [参考网址](http://www.cnblogs.com/demix/archive/2009/11/28/1612715.html)
  
  
  
  ##icon font制作 
     
  把制作好的AI图,另存为svg, 然后通过网址http://www.iconfont.cn/icons/uploadShow  上传, 点击加入购物车，然后再购物车中下载，会生成调用demo，进行对图片字段的调用。
  
  以上是icon font 字体的使用，下面介绍svg的应用。
  
  # SVG的应用
  
  
  
  
  
  
  
 
 
 
 








