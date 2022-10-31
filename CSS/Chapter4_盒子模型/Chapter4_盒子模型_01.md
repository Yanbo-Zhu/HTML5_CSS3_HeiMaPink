# 1 css学习三大重点：

 css 盒子模型 、 浮动 、 定位  
 
**网页布局的本质**

- 首先利用CSS设置好盒子的大小，然后摆放盒子的位置。    

- 最后把网页元素比如文字图片等等，放入盒子里面。

# 2 盒子中的属性

- content(内容): 盒子里面的文字和图片等元素是 内容区域

- border(边框): 盒子的厚度 我们称为为盒子的边框

- padding(内边距): 盒子内容与边框的距离是内边距

- margin(外边距): 盒子与盒子之间的距离是外边距
  ![](image/Chapter4_css_盒子模型_盒子模型的组成_001.png)
  ![](image/Chapter4_css_盒子模型_盒子模型的组成_002.png)

# 3 内盒尺寸 width,height,padding,border
## 3.1 盒子尺寸计算(元素实际大小)

- 宽度：Element Height = content height (元素名为 height， 不含有边框的高度)+ padding + border  （height 为 content 的高度）
- 高度：Element  Width = content width (元素名为 width 内容宽度, 不含有边框的宽度) + padding + border （Width为内容宽度）
- 盒子的实际大小：**内容的宽度和高度 +  内边距   +  边框**
- <mark> margin 不考虑在盒子的尺寸内， margin 不会撑大盒子的尺寸 </mark>

## 3.2 边框会额外增加盒子的实际大小
因此有两种方案解决。
1. 测量盒子大小的时候，不测边框。
2. 若测量的时候包含了边框，则需要 width/height-边框宽度。

## 3.3 盒子模型布局稳定性

优先使用  宽度 （width）  其次 使用内边距（padding）    再次  外边距（margin）
`width >  padding  >   margin`   

**原因：**

- margin 会有外边距合并 还有 ie6下面margin 加倍的bug（讨厌）所以最后使用。
- padding  会影响盒子大小， 需要进行加减计算（麻烦） 其次使用。
- width   没有问题（嗨皮）我们经常使用宽度剩余法 高度剩余法来做。

# 4 边框 border

border 可以设置元素边框。边框有三个组成：border-width、border-style、border-color

语法：

```
/*属性可连写*/
border: border-width || border-style || border-color;
```

| 属性           | 作用           |
| ------------ | ------------ |
| border-width | 定义边框粗细，单位 px |
| border-style | 边框样式         |
| border-color | 边框颜色         |

## 4.1 border-style
none：没有边框即忽略所有边框的宽度（默认值）
solid：边框为单实线(最为常用的)
dashed：边框为虚线
dotted：边框为点线

![](image/Chapter4_css_盒子模型_边框_style.png)

## 4.2 边框属性简写和分写

### 4.2.1 边框属性简写

```
顺序无所谓
/*习惯顺序*/ 
border: 5px solid pink;
```

### 4.2.2 边框属性分写

```
/*注意层叠性*/
border-top: 1px solid red;
border-buttom
border-left
border-right
```

很多情况下，我们不需要指定4个边框，我们是可以单独给4个边框分别指定的。

| 上边框                  | 下边框                      | 左边框                   | 右边框                    |
| -------------------- | ------------------------ | --------------------- | ---------------------- |
| border-top-style:样式; | border-bottom-style:样式;  | border-left-style:样式; | border-right-style:样式; |
| border-top-width:宽度; | border- bottom-width:宽度; | border-left-width:宽度; | border-right-width:宽度; |
| border-top-color:颜色; | border- bottom-color:颜色; | border-left-color:颜色; | border-right-color:颜色; |
| border-top:宽度 样式 颜色; | border-bottom:宽度 样式 颜色;  | border-left:宽度 样式 颜色; | border-right:宽度 样式 颜色; |

### 4.2.3 注意就近原则， 下面定义的会覆盖掉上面定义的
![](image/Chapter4_css_盒子模型_边框_简写_重叠性.png)

## 4.3 表格的细线边框 (合并相邻的边框)

border-collapse 属性控制浏览器绘制表格边框的方式。它控制相邻单元格的边框。

语法
border-collapse: collapse;

- collapse 是合并的意思
- border-collapse:collapse; 表示将相邻边框合并在一起

通过表格的`cellspacing="0"`,将单元格与单元格之间的距离设置为0. 
但是两个单元格之间的边框会出现重叠，从而使边框变粗
通过css属性：table{ border-collapse:collapse; } : `collapse` 单词是合并的意思,`border-collapse: collapse;`表示相邻边框合并在一起。

```css
<style> 
  table {  
   width: 500px;  
   height: 300px;  
   border: 1px solid red;  
   /* border-width:5px*/
   /* border-style:soild*/
   /* border-color:pink*/
 }  
 td {  
  border: 1px solid red;  
  text-align: center;  
 }  
 table, td， th {  
  border-collapse: collapse;  /*合并相邻边框*/  
  border: 1px solid pink;
  font-size: 14px
  text-aligh: center 
 }
 
 </style>
```


# 5 内边距 padding

padding 属性用于设置**内边距**,**即盒子边框与内容之间的距离**

| 属性             | 作用   |
| -------------- | ---- |
| padding-left   | 左内边距 |
| padding-right  | 右内边距 |
| padding -top   | 上内边距 |
| padding-bottom | 下内边距 |

## 5.1 padding属性(简写属性)

可以有一到四个值

| 值的个数                        | 表达意思                                           |
| --------------------------- | ---------------------------------------------- |
| padding : 5px;              | 1个值，上下左右。 代表上下左右都有5像素内边距                       |
| padding :5px 10px;          | 2个值，上下，左右。代表上下内边距是5像素，左右内边距是10像素               |
| padding: 5px 10px 20px;     | 3个值，上，左右，下。 代表上内边距5像素，左右内边距10像素，下内边距20像素       |
| padding :5px 10px 20px 30px | 4个值，上，右，下，左，顺时针。 上是5像素，右是10像素，下20像素，左是30像素，顺时针 |

## 5.2 padding 会影响盒子实际大小

如果盒子本身没有指定width/height属性，则此时padding不会撑开盒子大小 （让 padding 不影响盒子大小）

当盒子已经有了宽度 (width 元素 = 内容宽度)和 高度 （height 元素 = 内容高度），再指定内边距，会撑大盒子。整个盒子的宽高还需要再加上 padding 的宽高

当给盒子指定了 padding 值以后，发生了两件事情：
1. 内容和边框有了距离，增加内边距
2. padding 值影响了盒子实际大小
 

```
div {
width: 200px
height: 200px;
blackground-color: pink;
padding: 20px 
}
```

但是，有时候 padding 影响盒子是有好处的，比如我们要做导航： 因为每个导航栏里面的字数不一样多,我们可以不用给每个盒子宽度了,直接给 padding 最合适.
![](image/Chapter4_css_盒子模型_padding_001_例子导航栏.png)

### 5.2.1 解决方案， 让padding不会影响盒子实际大小：
1. 要保证盒子和效果图一样大，则让   width/height-多出来的内边距大小  即可。
2. 如果盒子本身没有指定width/height属性，则此时padding不会撑开盒子大小 （让 padding 不影响盒子大小）

#### 5.2.1.1 例子1
```css
<h1> {
/*width: 100% ;*/* // width 没有被指定
height: 200px;
bakcground-color: pink;
padding: 30px;  // 此时只有整个盒子的的高度被增长， 宽度没有被增长
}
```

#### 5.2.1.2 例子2 (重要)： 
这种情况下 p中没有直接给出 height 和 width， p继承 div 的 height 和 width, ， p 不会因为 p 的padding而变大， 会仍为300px x 100px: 

![](image/Chapter4_css_盒子模型_padding_004_例子4.png)
![](image/Chapter4_css_盒子模型_padding_004_例子5.png)

#### 5.2.1.3 例子3 (重要)： 
<mark> 孩子继承父亲的宽度，孩子设置padding 不会撑开盒子， 除非孩子自己设置了 height 和 width 元素  </mark>
这种情况下 p中直接给出  width， 没有直接给出 height
p继承 div 的 height 和 width。
但是  p这个盒子的整个 宽度会因为 子元素的padding而变大。高度不会会因为子元素padding而变大、   p 为230px x 100px: 
![](image/Chapter4_css_盒子模型_padding_005_例子6.png)
![](image/Chapter4_css_盒子模型_padding_006_例子7.png)

## 5.3 例子: 新浪导航栏
![](image/Chapter4_css_盒子模型_padding_004_例子3.png)
![](image/Chapter4_css_盒子模型_padding_002_例子1.png)
![](image/Chapter4_css_盒子模型_padding_003_例子2.png)

# 6 box-sizing 属性解决方案

- 在设置了一个盒子的 `width/height` 后，再设置其 `border/padding` 会影响盒子实际大小。当进行响应式布局时，这个尤其烦人。
- 若盒子没有指定 `width/height` 属性，则此时 `padding` 不会撑开盒子大小。



CSS 中的 `box-sizing` 属性定义了 `user agent` 应该如何计算一个元素的总宽度和总高度。
box-sizing 属性可以被用来调整这些表现。

### 6.1.1 content-box
`content-box` 是默认值。
在 设置了 box-sizing: content-box; 情况下， 如果你设置一个元素的宽为`100px`，那么这个元素的内容区会有 `100px` 宽，并且任何边框和内边距的宽度都会被增加到最后绘制出来的元素宽度中。
  
  ```
  box-sizing: content-box;
  ```

### 6.1.2 border-box
`border-box` 告诉浏览器：你想要设置的边框和内边距的值是包含在 `width` 内的。
也就是说，如果你将一个元素的 `width` 设为 `100px`，那么这 100px 会包含它的 `border` 和 `padding`，内容区的实际宽度是 `width` 减去 `(border + padding)` 的值。
大多数情况下，这使得我们更容易地设定一个元素的宽高。
  
  ```
  box-sizing: border-box;
  ```
  
  尺寸计算公式： 
  - `width = border + padding + 内容的宽度` 
  - `height = border + padding + 内容的高度`



# 7 外边距 margin

margin（外边距）属性用于设置外边距，即控制盒子和盒子之间的距离

## 7.1 margin 不会影响盒子的实际尺寸
- <mark> margin 不考虑在盒子的尺寸内， margin 不会撑大盒子的尺寸 </mark>
- <mark> 因为margin可用于大盒子中的 儿子盒子的分离， 而不用考虑对大盒子的影响  </mark>

## 7.2 margin的属性

| 属性            | 作用   |
| ------------- | ---- |
| margin-left   | 左外边距 |
| margin-right  | 右外边距 |
| margin-top    | 上外边距 |
| margin-bottom | 下外边距 |

![](image/Chapter4_css_盒子模型_margin_003_例子.png)

## 7.3 margin 简写属性

margin 简写方式代表的意义跟 padding 完全一致
可以有一到四个值

| 值的个数                       | 表达意思                                           |
| -------------------------- | ---------------------------------------------- |
| margin : 5px;              | 1个值，上下左右。 代表上下左右都有5像素外边距                       |
| margin :5px 10px;          | 2个值，上下，左右。代表上下外边距是5像素，左右外边距是10像素               |
| margin: 5px 10px 20px;     | 3个值，上，左右，下。 代表上外边距5像素，左右外边距10像素，下外边距20像素       |
| margin :5px 10px 20px 30px | 4个值，上，右，下，左，顺时针。 上是5像素，右是10像素，下20像素，左是30像素，顺时针 |

## 7.4 外边距典型应用

### 7.4.1 块级元素 水平轴方向上居中

外边距可以让块级盒子 **水平轴方向山给居中**，但是必须满足两个条件：

1. 盒子必须指定宽度（width）
2. 盒子左右的外边距都设置为 `auto`

```
.header {
  width: 960px;
  margin: 0 auto;
}
```

常见的写法，以下下三种都可以👇👇。

- margin-left: auto;   margin-right: auto
- margin: auto;
- margin: 0 auto;

### 7.4.2 行内元素和行内块元素 的水平居中 

1 行内元素和行内块元素是没有高度和宽度的， 所以下面这么定义的话， 对 span 是没有效果的 
![](image/Chapter4_css_盒子模型_margin_004_水平居中_例子.png)


2 如何使使行内元素或行内块元素水平居中
给行内元素和行内块元素 的 父元素添加  text-align: center;
1. 盒子内的文字水平居中是 text-align: center; 而且还可以让 行内元素和行内块居中对齐
2. 块级盒子水平居中  左右margin 改为 auto

##### 7.4.2.1.1 例子
![](image/Chapter4_css_盒子模型_margin_005_水平居中_例子.png)
![](image/Chapter4_css_盒子模型_margin_006_水平居中_例子.png)

![](image/Chapter4_css_盒子模型_margin_007_水平居中_例子.png)
### 7.4.3 插入图片和背景图片区别

1. `插入图片`我们用的最多 比如产品展示类  移动位置只能靠盒模型 padding margin

2. `背景图片`我们一般用于小图标背景或者超大背景图片、背景图片，移动位置只能通过  background-position

## 7.5 外边距合并

### 7.5.1 相邻元素垂直外边距的合并

当上下相邻块元素相遇时，若上面的元素有下外边距margin-bottom，下面的元素有上外边距margin-top，则他们之间的垂直间距不是 `margin-bottotm` 与 `margin-top` 之和。

取两个值中的较大者这种现象被称为相邻元素垂直外边距的合并。

解决方法： 「解决方案：尽量给只给一个盒子添加margin值」
![](image/Chapter4_css_盒子模型_margin_001_相邻元素垂直外边距的合并_01.png)

### 7.5.2 嵌套块元素垂直外边距的塌陷
使用 margin 定于块元素的水边外边距的时候， 可能会出现外边距的合并
![](image/Chapter4_css_盒子模型_margin_002_嵌套块元素垂直外边距的塌陷_02.png)
![](image/Chapter4_css_盒子模型_margin_002_嵌套块元素垂直外边距的塌陷_03.png)

对于两个嵌套关系（父子关系）的块元素，父元素有上外边距同时子元素也有上外边距，此时父元素会塌陷较大的外边距值。
在设置了子元素的 margin-top:10px后， 带着父元素的上边界一起向下平移了10px。 本来希望 父元素的上边界不动
此时谁的外边距大 ， 就塌陷谁的外边距。 
![](image/Chapter4_css_盒子模型_margin_002_嵌套块元素垂直外边距的塌陷_01.png)

解决方案
1. 方案1： 为父元素定义上边框
2. 方法2： 为父元素定义上内边距
3. 方法3： 为父元素添加 `overflow:hidden`
4. 还有其他方法，比如浮动、固定、绝对定位的盒子不会有塌陷问题。后面会进行总结。
before:
![](image/Chapter4_css_盒子模型_margin_002_嵌套块元素垂直外边距的塌陷_04.png)
正确的after
![](image/Chapter4_css_盒子模型_margin_002_嵌套块元素垂直外边距的塌陷_05.png)
错误的after 
![](image/Chapter4_css_盒子模型_margin_002_嵌套块元素垂直外边距的塌陷_06.png)

## 7.6 清除内外边距

网页元素很多都带有默认内外边距，而且不同浏览器默认的也不一致，因此在布局前，要先清除网页元素的内外边距。
注意：
- 块元素，和行内块元素 可以 随意设置 上下左右 内外边距
- 行内元素为了照顾兼容性，尽量只设置上下左右内边距，和设置左右外边距
    - 不要设置上下外边距, 设置了也根本不起作用
    - 但是转换为块级和行内块元素， 就可以设置随意这只上下左右 内外边距。


语法

```css
<style>
* {
  margin: 0; 清除外编剧
  padding: 0; 清除内边距
}
</style>
```

# 8 综合案例
## 8.1 案例 产品模块
![](image/Chapter4_css_盒子模型_综合案例_01_产品模块.png)

注意点

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>综合案例-产品模块</title>
    <style>
      * {
          margin: 0;
          padding: 0;
      }
      body {
          background-color: #f5f5f5;
      }
      a {
          color: #333;
          text-decoration: none;
      }
      .box {
          width: 298px;
          height: 415px;
          background-color:#fff;
          /* 让块级的盒子水平居中对齐 */
          margin: 100px auto;
      }
      .box img {
          /* 图片的宽度和父亲一样宽 , 不让图片超过盒子的大小*/
          width: 100%;
      }
      .review {
          height: 70px;
          font-size: 14px;
          /* 因为这个段落没有 width属性 所有 padding不会撑开盒子的宽度 */
          padding: 0 28px; /* 左右两个有些留白 */
          margin-top: 30px; /*  margin 不考虑在盒子的尺寸内， margin 不会撑大盒子的尺寸 */
      }
      .appraise {
          font-size: 12px;
          color: #b0b0b0;
          margin-top: 20px;
          padding: 0 28px;
      }
      .info {
          font-size: 14px;
          margin-top: 15px;
          padding: 0 28px;
      }
      .info h4 {
          display: inline-block;
          font-weight: 400;
         
      }
      .info span {
          color: #ff6700;    
      }
      .info em {
          font-style: normal;
          color: #ebe4e0;
          margin: 0 6px 0 15px;
      }
    </style>
</head>
<body>
    <div class="box">
        <img src="images/img.jpg" alt="">
        <p class="review">快递牛，整体不错蓝牙可以说秒连。红米给力</p>
        <div class="appraise">来自于 117384232 的评价</div>
        <div class="info">
               <h4> <a href="#">Redmi AirDots真无线蓝...</a></h4>
               <em>|</em>
               <span> 99.9元</span>
        </div>
    </div>
</body>
</html>
```
## 8.2 新闻快报
d:\File_Storage\File_Markdown\HTML5_CSS3_HeiMaPink_别人的笔记\基础部分\06-前端基础CSS第四天\案例\01-综合案例-新闻快报.html
![](image/Chapter4_css_盒子模型_综合案例_02_快报模块.png)

大盒子里面有两个小盒子 

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>新闻快报模块</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        li {
            /* 去掉 列表selector li前面的小圆点 */
            list-style: none;
        }

        .box {
            width: 248px;
            height: 163px;
            border: 1px solid #ccc;
            margin: 100px auto;
        }

        .box h3 {
            height: 32px;
            border-bottom: 1px dotted #ccc;
            font-size: 14px;
            font-weight: 400;
            line-height: 32px;
            padding-left: 15px;
            /* 这里不能用 margin-left: 15px; 来取代  padding-left: 15px; 
            padding-left: 15px; ：  因为 .box h3 中没有各处指定的width 的值， 所以 padding-left: 15px;  不会撑开盒子
            margin-left: 15px; 会使得 border-bottom 也和左边有了距离。 这个效果我们不想要。 
            我们只想要 品优购快报 这5个字和左边有距离 */ 
        }

        .box ul li a {
            font-size: 12px;
            color: #666;
            text-decoration: none;
        }

        .box ul li a:hover {
            text-decoration: underline;
        }

        .box ul li {
            height: 23px;
            line-height: 23px;
            padding-left: 20px;
        }

        .box ul {
            margin-top: 7px;
        }
    </style>
</head>

<body>
    <div class="box">
        <h3>品优购快报</h3>
        <ul>
            <li><a href="#">【特惠】爆款耳机5折秒！</a></li>
            <li><a href="#">【特惠】母亲节，健康好礼低至5折！</a></li>
            <li><a href="#">【特惠】爆款耳机5折秒！</a></li>
            <li><a href="#">【特惠】9.9元洗100张照片！</a></li>
            <li><a href="#">【特惠】长虹智能空调立省1000</a></li>
        </ul>

    </div>
</body>

</html>
```