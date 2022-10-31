# 1 HTML 的局限性

HTML 是网友的骨架，只关注内容的语义。例如`<h1>`表示大标题，`<p>`表示段落。

早期的时候，HTML 只能做一些简单的样式，网页非常丑，而且使 HTML 代码臃肿。

- HTML满足不了设计者的需求，可以将网页结构与样式相分离，这样就可以在不更改网页结构的前提下，更换网站的样式。

- 操作html属性不方便

- HTML里面添加样式带来的是无尽的臃肿和繁琐

# 2 css简介

CSS 最大价值: 由 HTML 专注去做结构呈现，样式交给 CSS，即 结构 ( HTML ) 与样式( CSS ) 相分离

 CSS 是层叠样式表 ( Cascading Style Sheets ) 的简称.
 有时我们也会称之为 CSS 样式表或级联样式表。
 CSS 是也是一种标记语言
 CSS 主要用于设置 HTML 页面中的文本内容（字体、大小、对齐方式等）、图片的外形（宽高、边框样式、边距等）以及版面的布局和外观显示样式。
 CSS 让我们的网页更加丰富多彩，布局更加灵活自如。简单理解：CSS 可以美化 HTML , 让 HTML 更漂亮， 让页面布局更简单。

# 3 css样式表引入方式

## 3.1 总结

![](.\image\Chapter1_Css简介_002_css引入方式.png)

## 3.2 行内样式表(行内式)

通过标签的style属性来设置元素的CSS样式. 适合于简单的样式修改

- style其实就是标签的属性

- 样式属性和值中间是:

- 多组属性值， 下载 “” 中， 之间直接用;隔开

- 只能控制当前的标签和以及嵌套在其中的字标签，造成代码冗余。

- **缺点:**没有实现样式和结构相分离。

```html
<标签名 style="属性1:属性值1; 属性2:属性值2; 属性3:属性值3;"> 内容 </标签名>
例如：
<div style="color: red; font-size: 12px;">青春不常在，抓紧谈恋爱</div>
```

## 3.3 内部样式表(内嵌式)

也称为内嵌式，将CSS代码集中写在HTML文档的head头部标签中，并且用style标签定义。

- style标签一般位于head标签中，当然理论上他可以放在HTML文档的任何地方。

- type="text/css"  在html5中可以省略。

- 只能控制当前的页面 的样式 

- **缺点:**没有彻底分离结构与样式

```html
<head>
<style type="text/CSS">
    选择器（选择的标签） { 
      属性1: 属性值1;
      属性2: 属性值2; 
      属性3: 属性值3;
    }
</style>
</head>
```

## 3.4 外部样式表(链接式)

```html
<head>
    <link rel="stylesheet" href="index.css">
</head>
```

  也称链入式，是将所有的样式放在一个或多个以.css为扩展名的外部样式表文件中，通过link标签将外部样式表文件链接到HTML文档中。

- `rel`:定义当前文档与被链接文档之间的关系，在这里需要指定为“stylesheet”，表示被链接的文档是一个样式表文件。

- `href`:定义所链接外部样式表文件的URL，可以是相对路径，也可以是绝对路径。

引入外部样式表的步骤

1. 新建一个.css 文件， 把所有的css 代码都放入此文件中

2. 在html 中， 通过 link 标签引入这个文件

# 4 css语法规范

1.使用 HTML 时，需要遵从一定的规范，CSS 也是如此。要想熟练地使用 CSS 对网页进行修饰，首先需要了解CSS 样式规则。
2.CSS 规则由两个主要的部分构成：<mark>选择器 以及 一条或多条声明</mark>。

![](./image/Chapter1_Css简介_001_css属性规则.png)

 1.选择器是用于指定 CSS 样式的 HTML 标签，花括号内是对该对象设置的具体样式
 2.属性和属性值以“键值对”的形式出现
 3.属性是对指定的对象设置的样式属性，例如字体大小、文本颜色等
 4.属性和属性值之间用英文“:”分开
 5.多个“键值对”之间用英文“;”进行区分

## 4.1 例子

    所有的样式，都包含在 <style> 标签内，表示是样式表。<style> 一般写到 </head> 上方

```cshtml
<head>
      <style>
          h4 {
              color: blue;
              font-size: 100px;
          }
      </style>
</head>
```

```cshtml
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>体验css语法规法</title>
    <style>
        p {  <!-- 给p这个标签定义样式 -->
            color: red;
            font-size: 20px;
        }

    </style>
</head>
<body>
    <p>
        Hallo
    </p>
</body>
</html>
```

# 5 css代码风格

- 展开式
- 选择器，属性名，属性关键字全部小写
- 空格规范

## 5.1 样式格式书写

2 紧凑格式  : 

```
h3 { color: pink; font-size: 20px;}
```

2 展开格式:  (强烈推荐这种格式， 因为更直观。)

```
h3 {
 color: pink;
 font-size: 20px;  
 }
```

## 5.2 样式大小写风格

1.小写格式强烈 (强烈推荐这种格式， 因为更直观。强烈推荐样式选择器，属性名，属性值关键字全部使用小写字母，特殊情况除外。)

    h3 {
         color: pink;
    }

 2 大写格式 

```
H3 {
 COLOR: PINK;
}
```

## 5.3 样式空格风格

属性值前面，冒号后面，保留一个空格 选择器（标签）和大括号中间保留空格

```
h3 {  // h3 后面有个空格 
 color: pink;  // 冒号后有一个空格 
}
```

# 6 CSS 属性书写顺序（重点）

1.  布局定位属性 (最开始写)：
    1. display / position / float / clear / visibility / overflow
    2. （建议 display 第一个写，毕竟关系到模式）    
2.  自身属性：
    1. width / height / margin / padding / border / background
3.  文本属性：
    1. color / font / text-decoration / text-align / vertical-align / white- space / break-word
4.  其他属性（CSS3）
    1. content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …

```css
.jdc {  
    display: block;  
    position: relative;  
    float: left;  
    width: 100px;  
    height: 100px;  
    margin: 0 10px;  
    padding: 20px 0;  
    font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;  
    color: #333;  
    background: rgba(0,0,0,.5);  
    -webkit-border-radius: 10px;  
    -moz-border-radius: 10px;  
    -o-border-radius: 10px;  
    -ms-border-radius: 10px;  
    border-radius: 10px;  
}
```