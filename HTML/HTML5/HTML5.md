# 笔记来源

[HTML5冲浪笔记(二)_生命是有光的的博客-CSDN博客](https://blog.csdn.net/Augenstern_QXL/article/details/115599059)

# HTML5 中新特性

- HTML5的新增特性主要是针对于以前的不足，增加了一些新的标签，新的表单和新的表单属性等。

- 这些新特性都有兼容性问题，基本都是IE9+以上版本的浏览器才支持，如果不考虑兼容性问题，可以大量使用这些新特性

- HTML5有更大的技术集，允许更多样化和强大的网站和应用程序。增加了新特性：语义特性，本地存储特性，设备兼容特性，连接特性，网页多媒体特性，三维、图形及特效特性，性能与集成特性，CSS3特性。这个集合有时称为HTML5和朋友，通常缩写为HTML5

# HTML5新增语义化标签

![](.\Image\HTML5_001_新增语义化标签.png)

这些新增的标签 都可以取代 div 标签 

- < header > :头部标签
- < nav >: 导航标签
- < article >： 内容标签
- < section >:定义文档某个区域
- < aside >:侧边栏标签
- < footer >: 尾部标签

**–注意：**

- 这种语义化标准主要是针对**搜索引擎**的
- 这些新标签页面中可以使用**多次**
- 在IE9中，需要把这些元素转换为**块级元素**
- 其实，移动端更喜欢使用这些标签

```html
<!DOCTYPE html>
<html lang="zh">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <style>
            header,
            nav {
                height: 120px;
                background-color: pink;
                border-radius: 15px;
                width: 800px;
                margin: 15px auto;
            }

            section {
                width: 500px;
                height: 300px;
                background-color: skyblue;
            }
        </style>
    </head>
    <body>
        <header>头部标签</header>
        <nav>导航栏标签</nav>
        <section>某个区域</section>
    </body>
</html>
```

# HTML5新增视频标签

多媒体标签分为 音频 **audio** 和视频 **video** 两个标签 使用它们，我们可以很方便的在页面中嵌入音频和视频，而不再去使用落后的flash和其他浏览器插件了。

因为多媒体标签的 属性、方法、事件比较多，因此我们需要什么功能的时候，就需要去查找相关的文档进行学习使用。

## video视频

当前 **<video>** 元素支持三种视频格式： mp4， Wav, ogg, 尽量使用 **mp4格式**

**使用语法：**

```html
 <video src="media/mi.mp4"></video>
```

![](.\Image\HTML5_006_video支持格式.png) 

### 针对不同的video格式的兼容写法

由于各个浏览器的支持情况不同，所以我们会有一种兼容性的写法，这种写法了解一下即可

```html
这种写法，浏览器会匹配video标签中的source，如果支持就播放，如果不支持往下匹配，直到没有匹配的格式，就提示文本

<video src="media/mi.mp4" controls="controls"  width="300">
    <source src="move.ogg" type="video/ogg" >
    <source src="move.mp4" type="video/mp4" >
    您的浏览器暂不支持 <video> 标签播放视频  //如果上两种格式， 阅览器都不支持， 就显示这句话： 您的浏览器暂不支持 <video> 标签播放视频
</video >
```

### video 常用属性

![](.\Image\HTML5_005_video常用属性.png) 

**属性很多，有一些属性需要大家重点掌握：**

- `autoplay` 自动播放
  - 注意： 在google浏览器上面，默认禁止了自动播放，如果想要自动播放的效果，需要设置 muted属性
- `width` 宽度
- `height` 高度
- `loop` 循环播放
- `src` 播放源
- `muted` 静音播放
- 一般不显示controls，让视频循环播放。 加上 controls 会显示 视频条， 音量大小按钮， 和箭头播放键 

**示例代码：**

```html
<video src="media/mi.mp4" autoplay="autoplay" muted="muted"  loop="loop" poster="media/mi9.jpg"></video>
```

## Audio音频

基本使用

当前元素支持三种视频格式： 尽量使用 **mp3格式**
![](.\Image\HTML5_002_audio支持格式.png) 

**使用语法：**

```html
<audio src="media/music.mp3"></audio>
```

#### 兼容写法

由于各个浏览器的支持情况不同，所以我们会有一种兼容性的写法，这种写法了解一下即可

```html
<audio  controls="controls"  >
    <source src="happy.mp3" type="audio/mpeg" >
    <source src="happy.ogg" type="audio/ogg" >
    您的浏览器暂不支持 <audio> 标签。  //如果上两种格式， 阅览器都不支持， 就显示这句话： 您的浏览器暂不支持 <audio> 标签
</audio>
```

**上面这种写法，浏览器会匹配audio标签中的source，如果支持就播放，如果不支持往下匹配，直到没有匹配的格式，就提示文本**

#### audio 常用属性

  ![](.\Image\HTML5_003_audio常用属性.png) 

不加上 autoplay="autoplay" ， 这个 音频就不会自动播放

**示例代码：**

```html
<audio src="media/music.mp3" autoplay="autoplay" controls="controls"></audio>
```

## 小结

- 音频标签和视频标签使用方式基本一致
- 浏览器支持情况不同
- 谷歌浏览器把音频和视频自动播放禁止了
- 我们可以给视频标签添加 muted 属性来静音播放视频，音频不可以（可以通过JavaScript解决）
- 视频标签是重点，我们经常设置自动播放，不使用 controls 控件，循环和设置大小属性

# HTML5新增的表单的 input类型

在H5中，帮我们新增加了很多类型的表单，这样方便了程序员的开发

在这个案例中，熟练了新增表单的用法

## html5之前的版本的 常见输入类型（input这个Attribute的 值)

```
text password radio checkbox button file hidden submit reset image
```

## HTML新增的输入类型（input这个Attribute的 值）

类型很多，我们现阶段**重点记忆三个**： **`number` `tel` `search`
![](.\Image\HTML5_007_input案例.png) 
![](.\Image\HTML5_008_新增input表单.png) 

案例代码：

```html
<!-- 我们验证的时候必须添加form表单域 -->
<form action="">
    <ul>
        <li>邮箱: <input type="email" /></li>
        <li>网址: <input type="url" /></li>
        <li>日期: <input type="date" /></li>
        <li>时间: <input type="time" /></li>
        <li>数量: <input type="number" /></li>
        <li>手机号码: <input type="tel" /></li>
        <li>搜索: <input type="search" /></li>
        <li>颜色: <input type="color" /></li>
        <!-- 当我们点击提交按钮就可以验证表单了 -->
        <li> <input type="submit" value="提交"></li>
    </ul>
</form>
```

# HTML5新增表单属性

![](.\Image\HTML5_009_新增表单属性.png)

```html
 <form action="">
        <input type="search" name="sear" id="" required="required" placeholder="pink老师" autofocus="autofocus" autocommplete="off">
        <input type="submit" value="提交">
    </form>
```

## 可以通过以下设置方式修改placeholder里面的字体颜色

```html
input::placeholder {
    color: pink;
}
```

![](.\Image\HTML5_010_placeholder里面的字体颜色1.png)

![](.\Image\HTML5_011_placeholder里面的字体颜色2.png)
