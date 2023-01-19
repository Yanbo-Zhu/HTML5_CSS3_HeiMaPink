

# 1 精灵图Sprites

核心原理：将网页中的一些小背景图像整合到一张大图中，这样服务器只需要一次请求就可以了
  
![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bRib7fONvzIh0zt2skNON8Fvj2NF43KNDc7BwY7vcItRGHiapGiczcg85Q/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

- 图所示为网页的请求原理图，当用户访问一个网站时，需要向服务器发送请求，网页上的每张图像都要经过一次请求才能展现给用户。
- 然而，一个网页中往往会应用很多小的背景图像作为修饰，当网页中的图像过多时，服务器就会频繁地接受和发送请求，造成服务器请求压力过大, 这将大大降低页面的加载速度。
    
**为什么需要精灵技术**：为了有效地减少服务器接受和发送请求的次数，提高页面的加载速度。

## 1.1 使用精灵图核心总结：
- 精灵图主要针对于小的背景图片使用。
- CSS 精灵其实是将网页中的一些背景图像整合到一张大图中（精灵图），然而，各个网页元素通常只需要精灵图中不同位置的某个小图，要想精确定位到精灵图中的某个小图。
- 这样，当用户访问该页面时，只需向服务发送一次请求，网页中的背景图像即可全部展示出来。


### 1.1.1 精灵图的具体实施
我们需要使用CSS的:
-   background-image、    
-   background-repeat
-   background-position属性进行背景定位，
-   其中最关键的是使用`background-position` 属性精确地定位。

首先我们知道，css精灵技术主要针对于背景图片，插入的图片img 是不需要这个技术的。
1.  精确测量，每个小背景图片的大小和 位置。
2.  给盒子指定小背景图片时， 背景定位基本都是 负值。


- 精灵图主要借助于背景位置来实现，此时可以使用 background-position
    - 移动的距离就是这个目标图片的x和y坐标，注意网页中的坐标有所不同（x轴右边走是正值，左边走是负值，y轴下边走是正值，上边走是负值）
- 一般情况下都是往上往左移动，所以数值是负值. 一般情况下精灵图都是负值。
    - 千万注意网页中的坐标： x 轴右边走是正值，左边走是负值， y 轴同理。

## 1.2 精灵图的缺点 
1.  图片文件还是比较大的
2.  图片本身放大和缩小会失真
3.  一旦图片制作完毕想要更换非常复杂

 此时，有一种技术的出现很好的解决了以上问题，就是字体图标 iconfont 字体图标可以为前端工程师提供一种方便高效的图标使用方式，
 iconfont 展示的是图标，本质属于字体。

## 1.3 滑动门出现的背景
制作网页时，为了美观，常常需要为网页元素设置特殊形状的背景，比如微信导航栏，有凸起和凹下去的感觉，最大的问题是里面的字数不一样多，咋办？

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bIKmUvSuib6aFic4Seia4jaorfGmEib2sf2V0eibBmF4r3yichjQzVMBOeibbA/640?wx_fmt=jpeg&wxfrom=5&wx_lazy=1&wx_co=1)\

为了使各种特殊形状的背景能够自适应元素中文本内容的多少，出现了CSS滑动门技术。它从新的角度构建页面，使各种特殊形状的背景能够自由拉伸滑动，以适应元素内部的文本内容，可用性更强。最常见于各种导航栏的滑动门。

#### 1.3.1.1 核心技术的例子

核心技术就是利用`CSS精灵`（主要是背景位置）和 `盒子padding`撑开宽度, 以便能适应不同字数的导航栏。

一般的经典布局都是这样的：

1.  a 设置 背景左侧，padding撑开合适宽度。
2.  span 设置背景右侧， padding撑开合适宽度 剩下由文字继续撑开宽度。
3.  之所以a包含span就是因为 整个导航都是可以点击的。

```html
<li>
  <a href="#">
    <span>导航栏内容</span>
  </a>
</li>
```

```css
* {  
    padding:0;  
    margin:0;  
  
   }  
    body{  
      background: url(images/wx.jpg) repeat-x;  
    }  
    .father {  
      padding-top:20px;  
    }  
    li {  
      padding-left: 16px;  
      height: 33px;  
      float: left;  
      line-height: 33px;  
      margin:0  10px;  
      background: url(./images/to.png) no-repeat left ;  
    }  
    a {  
      padding-right: 16px;  
      height: 33px;  
      display: inline-block;  
      color:#fff;  
      background: url(./images/to.png) no-repeat right ;  
      text-decoration: none;  
    }  
    li:hover,  
    li:hover a {  
      background-image:url(./images/ao.png);  
    }
```
# 2 字体图标iconfont
精灵图的缺点 , 解决方式就是字体图标 iconfont 
- 字体图标可以为前端工程师提供一种方便高效的图标使用方式，
- iconfont 展示的是图标，本质属于字体。

## 2.1 字体图标的优点
1. 轻量级：一个图标字体要比一系列的图像要小。一旦字体加载了，图标就会马上渲染出来，减少了服务器请求灵活性：本质其实是文字，可以很随意的改变颜色、产生阴影、透明效果、旋转等
2. 灵活性：本质其实是文字，可以很随意的改变颜色，产生阴影，透明效果，旋转等
3. 兼容性：几乎支持所有的浏览器，请放心使用 注意：字体图标不能替代精灵技术，只是对工作中图标部分技术的提升和优化。

## 2.2 什么时候使用字体图标或精灵图
1.  如果遇到一些结构和样式比较简单的小图标，就用字体图标。
2.  如果遇到一些结构和样式复杂一点的小图片，就用精灵图。

  
# 3 字体图标的使用步骤：
1.  字体图标的下载
2.  字体图标的引入(引入到我们html页面中)
3.  字体图标的追加(以后添加新的小图标)

## 3.1 字体图标的下载

外网： icomoon 字库 [http://icomoon.io](http://icomoon.io/)
IcoMoon 成立于 2011 年，推出了第一个自定义图标字体生成器，它允许用户选择所需要的图标，使它们成一字型。该字库内容种类繁多，非常全面，唯一的遗憾是国外服务器，打开网速较慢。
-   点击 IcoMoon App
-   选择需要的图标
-   点击`Generate Font`
-   点击 下载

阿里 iconfont 字库 [http://www.iconfont.cn](http://www.iconfont.cn/) 
这个是阿里妈妈 M2UX 的一个 iconfont 字体图标字库，包含了淘宝图标库和阿里妈妈图标库。可以使用 Al 制作图标上传生成。重点是，免费！

## 3.2 IconMoon 字体图标使用方法
1.  选择字体并下载. 将下载包解压，解压之后的文件如图
2.  将下载文件中的 fonts 文件夹复制到项目根目录下
    1. ![在这里插入图片描述](https://img-blog.csdnimg.cn/d02f2b4a81ff4e2ba3badc003fc0bea9.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)
3.  CSS样式中全局声明字体, 简单理解把这些字体通过css引入到我们页面中,
    1. 右键打开 style.css，这里我演示用notepad++打开，复制如图代码引入我们自己的CSS文件中
    2. ![在这里插入图片描述](https://img-blog.csdnimg.cn/7a25356ff5d543679fc846c54b1566b5.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)
    ```
    <style>
        @font-face {
             font-family: 'icomoon';
             src: url('fonts/icomoon.eot?7kkyc2');
             src: url('fonts/icomoon.eot?7kkyc2#iefix') format('embedded-opentype'),
             url('fonts/icomoon.ttf?7kkyc2') format('truetype'),
             url('fonts/icomoon.woff?7kkyc2') format('woff'),
             url('fonts/icomoon.svg?7kkyc2#icomoon') format('svg');
             font-weight: normal;
             font-style: normal;
        }
    </style>
    ```

4. html标签内添加小图标: 将 `style.css` 文件中的开头的字体声明代码赋值到 html 中
    1. 我们打开解压文件中的 demo.html ，复制想要的图标，粘贴进我们的 `<span></span>`标签中
  
![在这里插入图片描述](https://img-blog.csdnimg.cn/b54ee91dd0b74854a8afcce8b1bf37fb.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

5. 给标签定义字体
例如: 给 `span` 声明字体：
    ```css
    span {
      font-family: "icomoon";
    }
    ```
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/d03f4bec9701491ea0ecc0bd69d89f5a.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)
    注意：标签中的 `font-family` 的值和我们之前引入字体图标的`font-family` 必须一样，这里均为 icomoon
6.  打开 `demo.html`，复制页面中的方框图标到 html 代码中即可。
    所以我们的整体代码
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        @font-face {
            font-family: 'icomoon';
            src: url('fonts/icomoon.eot?7kkyc2');
            src: url('fonts/icomoon.eot?7kkyc2#iefix') format('embedded-opentype'), url('fonts/icomoon.ttf?7kkyc2') format('truetype'), url('fonts/icomoon.woff?7kkyc2') format('woff'), url('fonts/icomoon.svg?7kkyc2#icomoon') format('svg');
            font-weight: normal;
            font-style: normal;
        }
        
        span {
            font-family: "icomoon";
        }
    </style>
</head>

<body>
    <div>
        <span> </span>
    </div>
</body>

</html>

```

最终效果: 
![在这里插入图片描述](https://img-blog.csdnimg.cn/fac058a088f2454ba22fcb0c99ee679d.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

## 3.3 字体图标的追加
-   如果工作中，原来的字体图标不够用了，我们需要添加新的字体图标到原来的字体文件中。
-   以 icomoon字库 网为例，点击网站内`import icons`
-   把压缩包里面的 selection.json 重新上传，然后选中自己想要新的图标，重新下载压缩包，并替换原来的文件即可。(更换 `@font-face` 内容。)
![在这里插入图片描述](https://img-blog.csdnimg.cn/136b1488a4cb4233ad7ff77f5f9deb44.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

## 3.4 字体文件格式
不同浏览器所支持的字体格式是不一样的，字体图标之所以兼容，就是因为包含了主流浏览器支持的字体文件。
.ttf 格式、.woff 格式、.eot 格式、.svg 格式，不同浏览器支持不同的格式

![在这里插入图片描述](https://img-blog.csdnimg.cn/ec0439450c03456483a147d5b0eafef5.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

