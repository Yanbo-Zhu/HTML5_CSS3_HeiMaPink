
# 1 通过设置 来Using device pixels

出现的问题: 
Pixels are relative!  Compare the resolution of your desktop and your phone. 
CSS-pixels are rendered on your device. If you develop on your desktop and make your viewport smaller or larger. it's still on your desktop! It won't work on a handheld device.

解决方式 使用 meta-tag 获得 相对的 width 
Use your meta-tag to set the CSS-width equal to the device-width.
```css
meta name="viewport" content="width=device-width"


==========
<head>
    <meta charset="utf-8">
    <title>Media Queries</title>
    <meta name="viewport" content="width=device-width">
    <link rel="stylesheet" href="styles/02rwdMediaQueries.css">
</head>
```

# 2 媒体查询 Media Query

"https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries" 

媒体查询（Media Query）是CSS3新语法。
With media queries we can ask for certain types of output and additional features. Depending on those we can change styles for these features.
<mark>Media Queries are stylesheets within stylesheets.</mark>

- 使用 @media 查询，可以针对不同的媒体类型定义不同的样式
- @media 可以针对不同的屏幕尺寸设置不同的样式
- 当你重置浏览器大小的过程中，页面也会根据浏览器的宽度和高度重新渲染页面
- 目前针对很多苹果手机、Android手机，平板等设备都用得到多媒体查询

Organizing media queries within a stylesheet
- There is no right or wrong way to organize media queries.
- 可以all rules 都写在 一个 media query, 或者每个 rule 都写着再单独的一个 media query: Be consistent! You can write all rules within one media query or you can write a media query just after each separate rule that needs one.

## 2.1 语法
```css
@media not|only mediatype and (mediafeature and|or|not mediafeature) {
  CSS-Code;
}
```


- 用 @media 开头 注意@符号
- mediatype 媒体类型
- keyword :  and, not, only
- mediaFeature 媒体特性 必须有小括号包含

使用的时候注意点
- <mark>不指定 mediatype,  则作用于全部的各种类型的mediatype. </mark>  If you don't include a type it will target to all types (screen, print, ...)
- 注意mediatype 是大小写敏感的，只能是小写;
- 尽量少用 median query.   因为总是界面变化, 会增加 client 和 server 之间的访问量 

## 2.2 例子
下面代码的意思是在我们屏幕上页面处于 500px-800px 之间，页面背景颜色显示为 pink 色。页面小于 500px，背景颜色显示为 purple 色

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        /* 这句话的意思就是： 在我们屏幕上 并且 最大的宽度是 800像素 设置我们想要的样式 */
        /* max-width 小于等于800 */
        /* 媒体查询可以根据不同的屏幕尺寸在改变不同的样式 */

        @media screen and (max-width: 800px) {
            body {
                background-color: pink;
            }
        }

        @media screen and (max-width: 500px) {
            body {
                background-color: purple;
            }
        }
    </style>
</head>
```

## 2.3 Keyword (and, not ,only)

关键字将媒体类型或多个媒体特性连接到一起做为媒体查询的条件。

- and：可以将多个媒体特性连接到一起，相当于"且"的意思。
- not：排除某个媒体类型，相当于"非"的意思，可以省略。
- only：指定某个特定的媒体类型，可以省略。


## 2.4 mediatype (媒体类型)

将不同的终端设备划分成不同的类型，称为媒体类型

- <mark>不指定 mediatype,  则作用于全部的各种类型的mediatype. </mark>  If you don't include a type it will target to all types (screen, print, ...)
- 注意mediatype 是大小写敏感的，只能是小写;


### 2.4.1 常用的 media type

all：適用於所有裝置
screen：主要用於彩色電腦螢幕 (包含手機和平版)
speech：適用於語音合成器 (speech synthesizer)、語音朗讀裝置
print：適用於 paged material 和在列印預覽模式下在螢幕上查看的文件，例如：用瀏覽器的「列印預覽」模式察看文件 

```css
@media print {
  body { font-size: 10pt; }
}
@media screen {
  body { font-size: 13px; }
}
@media screen, print {
  body { line-height: 1.2; }
}
```


### 2.4.2 媒体类型为print( @media print )
medien print 中设置, 只是打印机打印出来的时候, 页面长啥样 . 
    - 可以用 pdf 打印阅览, 来查看效果 
- media print 中的设置, 无关于 这个页面在阅览器中显示的, 长啥样  

#### 2.4.2.1 语法
```css
@median print {
    #menu a {
        display: none;
    }
}
```

#### 2.4.2.2 例子
```css
@media print {
    #menu a{
        display: none;
    }
    main{
        display: block;
    }

    article{
        background: hsl(0 0% 100%);
        border: none;
        margin: auto;
        width: 100%;
        page-break-inside: avoid;
    }
    :root{
        font-size: 12px;
        font-family: serif;
    }

    a{
        text-decoration: none;
        color: hsl(0 0% 0%);
    }
     a[href]::after{
        content: attr(href);
        display: block;
    }
    nav{
        display: none;
    }

}

```

### 2.4.3 媒体类型为screen (@media screen)

- @media screen 是设置 页面在显示器中显示成什么样, 
- 对于打印网页的时候, 打印出来的效果, @media screen 中的设置是无效的. 


```css
@media screen and (prefers-color-scheme: dark){  // and (prefers-color-scheme: dark 说的是 当系统是 深色模式的时候, 这个设置才有效. ,如果系统为 为白色模式, 这个设置失效

    body{
        blockground : hsl(1 0% 0%);
        color: hsl (); 
    }

    article{
        border-color: hsl (0 0% 100)
    }
}
```



## 2.5 媒体特性 (media Feature)

每种媒体类型都具体各自不同的特性，根据不同媒体类型的媒体特性设置不同的展示风格。

注意他们要加小括号包含。

| 值         | 解释                |
|---------|-----------------|
| width     | 定义输出设备中页面可见区域的宽度. the viewport width  |
| height | the viewport height |
| min-width | 定义输出设备中页面最小可见区域宽度. 下面块中效果能够生效的最小宽度 <br> 阅览器的窗口通过鼠标扩大, 直到阅览器的 view area 大于这个 设定好的值的时候, 定义的效果就生效了, |
| max-width | 定义输出设备中页面最大可见区域宽度. 下面块中效果能够生效的最大宽度 <br> 阅览器的窗口通过鼠标扩大, 直到 阅览器的 view area 大于这个 设定好的值的时候, 定义的效果就失效了, 不起作用了 |
| device-width | the viewport width of the specific device. it will be deprecated in Media Queries Level 4 |
| device-height | the viewport height of the specific device. it will be deprecated in Media Queries Level 4 |
| orientation | landscape or portrait orientation of the device |
| aspect-ratio | the ration of width to height |

### 2.5.1 min-width 和 max-width的比较 
- min-width means from this width and larger, so it's for a large(r) screen.  阅览器的 view area 必须大于这个值的时候, 这个设置才生效
- max-width works the other way around.  阅览器的 view area 必须小于这个值额时候, 这个设置才生效
- You can also work within a range between min-width and max-width.
<br>
1. Working with <code>min-width</code> means you are working desktop-first.
2. Working with <code>max-width</code> means you are working Mobile-first.
<br>
The order of media queries is important! 
- If you work with <code>min-width</code>, you work from the smallest to the biggest.
-  <em>Try the whole stylesheet mobile-first!</em></p>

#### 2.5.1.1 min-width, max-width 的例子 

例子1 
```css
@media (max-width: 75em){
    h1{
        text-align: center;
    }
}

@media (max-width:45em){
    p{
        font-size: 1.8rem;
        line-height: 1.3;
        background: hsl(0 0% 95%);
    }

    h2,
    h3{
        font-size: 2rem;
        text-align: center;
    }
   
}
```


例子2
注意： 为了防止混乱，媒体查询我们要按照从小到大或者, 从大到小的顺序来写,但是我们最喜欢的还是从小到大来写，这样代码更简洁

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
    
        /* 1. 媒体查询一般按照从大到小或者 从小到大的顺序来 */
        /* 2. 小于540px 页面的背景颜色变为蓝色 */
        @media screen and (max-width: 539px) {
            body {
                background-color: blue;
            }
        }



        /* 3. 540 ~ 970 我们的页面颜色改为 绿色 */
        /* @media screen and (min-width: 540px) and (max-width: 969px) {
            body {
                background-color: green;
            }
        } */
        @media screen and (min-width: 540px) {
            body {
                background-color: green;
            }
        }



        /* 4. 大于等于970 我们页面的颜色改为 红色 */

        @media screen and (min-width: 970px) {
            body {
                background-color: red;
            }
        }




        /* 5. screen 还有 and 必须带上不能省略的 */
        /* 6. 我们的数字后面必须跟单位  970px   这个 px 不能省略的 */
    </style>
</head>
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/9ebceb16c2f04d2da6d4425202bf1b86.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA55Sf5ZG95piv5pyJ5YWJ55qE,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)


## 2.6 Breakpoints (design 在那个像素点变化)

Breakpoints are the width at which we want to change the design.
Don't use standard breakpoints. Better, look at the screen and decide at what point does the layout look wrong. It depends on your design. Try different breakpoints.
Don't target specific devices, because there are just too many.

For maintainability keep the breakpoints to a minimum. 
- The more breakpoints you have, the more adjustments you have to make, if you are making changes to on breakpoint.


  

# 3 prefers-color-scheme
https://developer.mozilla.org/zh-CN/docs/Web/CSS/@media/prefers-color-scheme

W3C 在 2020 年 7 月 31 日发布的 [Media Queries Level 5 标准草案](https://www.w3.org/TR/mediaqueries-5/) 中提到了新的属性 `prefers-color-scheme`，网页现在可以通过条件规则组来 <mark>获取浏览器宿系统的暗色模式状态</mark>并应用了。
也就是说
1. 现在 页面可以知道 阅览器的宿主系统(就是操作系统), 现在处于那种模式下. 
2. 然后通过 prefers-color-scheme可以, 实现
    2. 如果宿主系统为暗色模式, 则 `@media screen and (prefers-color-scheme: dark)` 块中的设置, 生效, 
    3. 如果宿主系统为亮色模式, 则 `@media screen and (prefers-color-scheme: light)` 块中的升值, 生效, 

## 3.1 properties 
prefers-color-scheme 有 2 种值：
- light——浏览器宿系统使用亮色主题的界面，同时也是默认值，浏览器 privacy.resistFingerprinting 被设置为 true 时返回的也将是这个值
- dark——浏览器宿系统使用暗色主题的界面


还有一个已废弃的值：
- no-preference——浏览器宿系统使用未知主题的界面，
    - 当较旧版本的浏览器在宿系统不支持系统层级的暗色模式时会返回这个值，较旧版本的浏览器 privacy.resistFingerprinting 被设置为 true 时返回的也将是这个值

## 3.2 语法
CSS: 
```css
@media (prefers-color-scheme: dark) {
  // 暗色模式样式
}
@media not (prefers-color-scheme: dark) {
  // 非暗色模式样式
}


===

@media (prefers-color-scheme: dark) {
  body {
    background: #222;
    color: #eee;
  }
  html {background: #111;}
  body {background-color: #272727; color: #fff;}
  a {color: #50a8d8}
}
```

JavaScript
只使用 CSS 条件规则很难实现某些需求，我们可以对 window 使用 matchMedia 方法得到的 Media 使用 matches 方法来获取系统暗色模式状态：
```js
if (window.matchMedia('prefers-color-scheme: dark').matches) {
  // 是暗色模式做什么
} else {
  // 非暗色模式做什么
}
```

另外还可以监听系统暗色模式的状态，在系统开关暗色模式时作出反应：

```js
window.matchMedia('(prefers-color-scheme: dark)').addListener(e => {
  if (e.matches) {
    // 系统开启暗色模式后做什么
  } else {
    // 系统关闭暗色模式后做什么
  }
});

```
