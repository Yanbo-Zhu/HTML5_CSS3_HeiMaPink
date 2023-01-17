# 1 CSS 用户界面样式

所谓的界面样式，就是更改一些用户操作样式，以便提高更好的用户体验。

- 更改用户的鼠标样式
- 表单轮廓
- 防止表单域拖拽



| 属性   | 用途            | 用途                                    |
| ---- | ------------- | ------------------------------------- |
| 鼠标样式 | 更改鼠标样式cursor  | 样式很多，重点记住 pointer                     |
| 轮廓线  | 表单默认outline   | outline 轮廓线，我们一般直接去掉，border是边框，我们会经常用 |
| 防止拖拽 | 主要针对文本域resize | 防止用户随意拖拽文本域，造成页面布局混乱，我们resize:none    |

## 1.1 鼠标样式 cursor

-设置或检索在对象上移动的鼠标指针采用何种系统预定义的光标形状

```css
cursor: default | pointer | move | text | not-allowed;
```

| 属性值         | 描述    |
| ----------- | ----- |
| default     | 小白，默认 |
| pointer     | 小手    |
| move        | 移动    |
| text        | 文本    |
| not-allowed | 禁止    |

```css
<ul>  
  <li style="cursor:default">我是小白</li>  
  <li style="cursor:pointer">我是小手</li>  
  <li style="cursor:move">我是移动</li>  
  <li style="cursor:text">我是文本</li>  
  <li style="cursor:not-allowed">我是文本</li>  
</ul>
```

## 1.2 表单轮廓 outline

![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bdicbvJ2vdWvVm9PuHt5WLFn7XqYAx60k0El53qx9JfgLB734At4Ru9w/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)
是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。

```css
outline : outline-color ||outline-style || outline-width 
```

但是我们都不关心可以设置多少，我们平时都是去掉的。最直接的写法是 ： outline: 0;   或者   outline: none;
给表单添加 outline:0; 或者outline: none;样式后，就可以去掉默认的蓝色边框

```css
input {
  outline: none;
}
```

## 1.3 文本域缩放 resize

防止拖拽文本域resize
![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bHX3RwpjHtdppaZKxrEhq5QjZB339Zn5b7xMvy2XsrPblC9V7Z478JQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

```css
textarea {
  outline: none;
  resize: none;
}

==============
<textarea  style="resize: none;"></textarea>
```

# 2 align

## 2.1 其他类型的居中
-   有宽度的块级元素居中对齐，是margin: 0 auto;
-   让文字居中对齐，是 text-align: center;

## 2.2 vertical-align

`vertical-align` 指定行内/行内块元素的元素的垂直对齐方式。

- 使用场景：经常用于设置**图片**或者**表单（行内块元素）**和**文字垂直对齐**。
- 官方解释：用于设置一个元素的垂直对齐方式，但是它只针对于**行内元素**或者**行内块元素**有效
    - 特别是行内块元素， 通常用来控制图片/表单与文字的对齐。

### 2.2.1 属性值

vertical-align: baseline | top | middle | bottom

| 值        | 描述                        |
| -------- | ------------------------- |
| baseline | 默认，元素放置在父元素的基线上           |
| top      | 把元素的顶端与行中最高元素的顶端对齐（顶线对齐）  |
| middle   | 把此元素放置在父元素的中部（中线对齐）       |
| bottom   | 把元素的顶端与行中最低的元素的顶端对齐（底线对齐） |

![在这里插入图片描述](https://img-blog.csdnimg.cn/2f7832a64527405181bd3edbcd3a736a.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bX32nStNY16aY9odqroA3Mpia6nia2fuh9DYmYCszG7V1to2VsNwibY8Sg/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

### 2.2.2 图片、表单和文字居中对齐 vertical-align (vertical-align: middle)

图片、表单都属于行内块元素，默认的 vertical-align 是基线对齐。
此时可以给图片、表单这些行内块元素的 vertical-align 属性设置为 middle 就可以让文字和图片垂直居中对齐了。

```css
img {
  vertical-align: middle;
}
li {
  disaplay: inline-block;
  vertical-align: middle;
}
```

#### 2.2.2.1 重点

vertical-align：middle的作用机制就是对齐基线，这里之所以<mark>要设置line-height（最关键的）就是要让首行匿名元素（空白节点）处于父容器基线左右的位置</mark>，然后内联元素设置了vertical-align:middle才会对齐这个节点，否则是无效的！！！！

![在这里插入图片描述](https://img-blog.csdnimg.cn/159dbd0d98f941f5b17eb713341d3c64.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

您可以狠狠地点击这里：[CSS3 width:fill-available下的垂直居中demo](https://www.zhangxinxu.com/study/201605/width-fill-available.html)

![块状元素尺寸表现内联元素垂直居中行为](https://image.zhangxinxu.com/image/blog/201605/2016-05-20_004332.png)

完整关键CSS代码如下：

```css
.box {
    height: 200px; 
    /* 行高控制垂直居中 */
    line-height: 200px;
}
.fill-available {
    /* 元素内联，响应行高和vertical-align控制 */
    display: inline-block;
    vertical-align: middle;

    /* 宽度如块状元素般表现 */
    width: -webkit-fill-available;
    width: -moz-fill-available;
    width: -moz-available;    /* FireFox目前这个生效 */
    width: fill-available;
}
```

### 2.2.3 解决图片底部默认空白缝隙问题

bug ：图片底侧会有一个空白缝隙，原因是行内块元素会和文字的基线对齐。给图片加边框就可以看见
![在这里插入图片描述](https://img-blog.csdnimg.cn/6ab28389075f4478a70a11cae3e5a58e.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)
![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8boGWdjhQUvkicibGiaRYd0KDL2Y1kmqWLl75piaeMlRTMVh4go056Pj1OLA/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)


主要解决方法有两种：

1. 给图片添加 `vertical—align: middle topl bottom;` 等。（提倡使用的）
    1. ![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bNO8sogwyKtqHT6Bg0iaDeAkWqlbbSWqKJIGqtt8As1oFz17wBkQYb4g/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)
2. 把图片转换为块级元素 `display: block；`, 给img 添加 display：block; 转换为块级元素就不会存在问题了。

## 2.3 horizontal-align

# 3 溢出文字省略显示
## 3.1 white-space

white-space设置或检索对象内文本显示方式。通常我们使用于强制一行显示内容    
`white-space:normal ；默认处理方式     `
`white-space:nowrap ； 强制在同一行内显示所有文本，直到文本结束或者遭遇br标签对象才换行。   `

## 3.2 text-overflow 文字溢出

设置或检索是否使用一个省略标记（...）标示对象内文本的溢出
`text-overflow : clip ；不显示省略标记（...），而是简单的裁切       `
`text-overflow：ellipsis ； 当对象内文本溢出时显示省略标记（...）   `

**「注意」**： 一定要首先强制一行内显示，再次和overflow属性  搭配使用

![图片](https://mmbiz.qpic.cn/mmbiz_png/y7EkeCWAzmqtcdL7HZYccBic0jicaWzR8bJMSFBl0zS6bbLaYbicsptgr6KC0uTOEBhZViaFYNY96FibxUF3Xp3fReQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

## 3.3 用例
### 3.3.1 单行文本溢出省略号显示

```css
/*1·先强制一行内显示文本*/ 
white-space: nowrap;   /*默认 normal 是自动换行，nowrap是强制一行显示文本*/

/*2·超出的部分隐藏*/ 
overflow: hidden; 

/*3.文字用省略号替代超出的部分*/ 
text-overflow: ellipsis;  /*ellipsis:省略号*/
```

### 3.3.2 多行文本溢出显示省略号显示

多行文本溢出显示省略号，有较大的兼容性问题，适合于webKit浏览器或移动端(移动端大部分是webKit内核)
更推荐让后台人员来做这个效果，因为后台人员可以设置显示多少个字，操作更简单。

```css
overflow: hidden;
text-overflow: ellipsis;

/* 弹性伸缩盒子模型显示 */
display: -webkit-box;

/* 限制在一个块元素显示的文本的行数 */
-webkit-line-clamp: 2;

/* 设置或检索伸缩盒对象的子元素的排列方式 */
-webkit-box-orient : vertical;
```

# 4 常见布局技巧

## 4.1 margin负值的运用

1. 解决并排盒子之间的边框宽度加倍问题。 原理：让每个盒子压住前面的盒子，边框叠加。
2. 鼠标移动边框颜色变化效果。

### 4.1.1 有两个盒子

- 两个盒子加边框1px，浮动，贴紧会出现 1 + 1 = 2px
- 给右边盒子添加`margin-left: -1px`
- 正数向右边走，负数向左边走
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/49161c07333346c990eab8dca70b4425.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

### 4.1.2 有多个盒子

https://blog.csdn.net/Augenstern_QXL/article/details/119172527

![在这里插入图片描述](https://img-blog.csdnimg.cn/8bf8e78f78bf4dfa89950aa8dd76bfd6.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)
当我们有多个盒子时的解决办法：

1. 让每个盒子 margin 往左侧移动 -1px 正好压住相邻盒子边框
2. 鼠标经过某个盒子的时候，提高当前盒子的层级即可
   - 如果没有定位，则加相对定位(保留位置)
   - 如果有定位，则加 z-index

```csss
/*如果盒子没有定位，则鼠标经过添加相对定位即可*/
ul li:hover {
  position: relative;
  border: 1px solid orange;
}
/*若li都有定位，则使用 z-index 提高层级*/
ul li {
  z-index: 1;
  border: 1px solid orange;
}
```

```html
<head>
<style>
    ul li {
        float: left;
        list-style: none;
        width: 150px;
        height: 200px;
        border: 1px solid red;
        margin-left: -11px
    }

    ul li:hover {
        position: relative;
        border: 1px solid blue;
    }

</style>
</head>
<body>
    <ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
    </ul>
</body>
```

## 4.2 文字围绕浮动元素巧妙运用

原理：浮动元素不会遮住文字。

```
div {
  float: left;
}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/71377b1f43f34ff1aaf153cf1dceb0b6.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

## 4.3 行内块元素巧妙运用

![在这里插入图片描述](https://img-blog.csdnimg.cn/7d1aaaf6a6d549e7b1a90c25447fb370.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

行内块元素布局当前页码和 pre，next盒子，使用 text-align: center 居中。
页码在页面中间显示：

1. 把这些链接盒子转换为行内块，之后给父级指定 `text-align: center`
2. 利用行内块元素中间有缝隙，并且给父级添加 `text-align: center` ，行内块元素会水平居中
