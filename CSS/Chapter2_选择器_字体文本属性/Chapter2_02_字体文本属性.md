# 1 CSS字体属性

## 1.1 字体属性总结

| 字体属性        | 表示   | 注意                                                                |
| ----------- | ---- | ----------------------------------------------------------------- |
| font-size   | 字号   | 单位是 `px`. 我们通常用的单位是 px ，一定要跟上单位                                   |
| font-family | 字体   | 按照团队约定来写                                                          |
| font-weight | 字体粗细 | 400=normal，700=bold. 加粗是 700 或者 bold ，不加粗是 normal 或者 400，记住数字不加单位 |
| font-style  | 字体样式 | italic，normal，常用 normal. 记住倾斜是 italic，不倾斜是 normal，实际开发最常用 normal  |
| font        | 属性连写 | 顺序不能变，字体和字号属性必须有                                                  |

## 1.2 字体系列 font-family

CSS 使用 `font-family` 属性定义文本字体系列。

可以制定多个字体

- 各种字体之间必须使用英文状态下的逗号隔开

- 一般情况下，如果有空格隔开的多个单词组成的字体，加引号

- 尽量使用默认字体，保证不同浏览器的兼容性

最常见的几个字体：

```css
<style>
body {
  font-family: "微软雅黑", Arial, Helvetica, sans-serif;
}

div { 
    font-family:Arial,"Microsoft Yahe","微软雅黑"; 
}

h2 {
    font-family:Arial;
}

</style>
```

## 1.3 字体大小 font-size

CSS 使用 `font-size` 属性定义字体大小。

- `px` 大小是我们网页常用单位
- 默认是 `16px`. 如果没有重置，html默认font-size:16px。
- 可以给 `body` 指定整个页面文字大小。 不同浏览器可能默认显示的字号大小不一致，我们尽量给一个明确值大小，不要默认大小。一般给body指定整个页面文字的大小。

语法：

```
p {
  font-size: 16px;
}
```

### 1.3.1 字体大小单位

![](.\image\Chapter2_css_文字属性_001_字体大小单位.png)

| type                                                         | content                                                                                                                                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| absolut                                                      | px: vermeiden! Wenn, dann für kleine Werte, min- oder max - Angaben <br>pt                                                                                               |
| relativ: zum parent                                          | em: 1em 等于当前的字体尺寸。 2em 等于当前字体尺寸的两倍。 例如，如果某元素以 12pt 显示，那么 2em 是24pt。 在 CSS 中，em 是非常有用的单位，因为它可以自动适应用户所使用的字体。 <br> ex: 一个 ex 是一个字体的 x-height。 (x-height 通常是字体尺寸的一半。) <br> % |
| relativ: zum html also zum root-Element                      | rem: rem表示“Root EM”,字面上指的是根元素的em大小。                                                                                                                                      |
| <br/>在Web文档的上下文中，根元素就是你的html元素。 如果没有重置，html默认font-size:16px。 |                                                                                                                                                                          |
| relativ: im grid                                             | fr                                                                                                                                                                       |
| relativ: zum viewport. Sie sind von der Bildschirmgröße abhängig.                                      | vw(viewport width), vh (viewport height), vmin, vmax                                                                                                                                                       |

### 1.3.2 em 和 rem比较

| 单位  | 特点                                                                                 |
| --- | ---------------------------------------------------------------------------------- |
| em  | 相对单位em是相对于元素本身的字体大小的。 在css中唯一例外的是font-size属性，它的em和ex值指的是相对父元素的字体大小。 不是这个元素本身的字体大小的 |
| rem | 集相对大小和绝对大小的优点于一身， 通过它既可以做到只修改根元素就成比例地调整所有字体大小， 又可以避免（使用em）字体大小逐层复合的连锁反应            |

em 缺点

- em 的值并不是固定的；
- 对于 font-size 属性。 em 会继承父级元素的字体大小。
  - <mark>在css中唯一例外的是font-size属性，它的em和ex值指的是相对父元素的字体大小。 不是这个元素本身的字体大小的</mark>
- 对于其他属性， em 是相对于本元素自己的字体属性(font-size) 的大小

rem 使用小技巧： body选择器中声明Font-size=62.5%; 。 将你的原来的px数值除以10，然后换上rem作为单位；

### 1.3.3 例子

```css
body{
  font-size: 10px;
}
h2{
  display: block;
  width: 80%;
  font-size: 1.5em;
  margin: 0.5em;
}
```

h2的字体大小继承了body字体， 10px * 1.5 = 15px  （因为 h2 标签， 通常是写在 body 标签里面的 ）
h2的margin属性则是相对于本元素字体大小： 15px * 0.5 = 7.5px

![](.\image\Chapter2_css_文字属性_004_fontSize属性_例子.png)

### 1.3.4 CSS Unicode字体

- 在 CSS 中设置字体名称，直接写中文是可以的。但是在文件编码（GB2312、UTF-8 等）不匹配时会产生乱码的错误。

- xp 系统不支持 类似微软雅黑的中文。

- 解决方案：英文来替代。比如`font-family:"Microsoft Yahei"`。在 CSS 直接使用 Unicode 编码来写字体名称可以避免这些错误。使用 Unicode 写中文字体名称，浏览器是可以正确的解析的。

`font-family: "\5FAE\8F6F\96C5\9ED1";   表示设置字体为“微软雅黑”。`   

## 1.4 字体粗细 font-weight

CSS 使用 `font-weight` 属性设置字体粗细

```html
font-weight:  normal | bold |  bolder  | lighter |number
```

| 属性值     | 描述                                     |
| ------- | -------------------------------------- |
| normal  | 默认值(不加粗的)，相当于**number=400**            |
| bold    | 定义粗体(加粗的)，相当于**number=700**            |
| bolder  | 定义特粗体                                  |
| 100-900 | 400等同于 normal，700等同于 bold，注意这个数字后面不跟单位 |

```
p {
  font-weight: 700;
等效于 font-weight: bold;
}
```

实际开发中，更常用数字来表示加粗或变细。`400`为`normal`，`700` 为 `bold`。 |属性值|描述| |-|-| |normal|默认值| |bold|定义粗体| |100-900|400 等价于 normal，700 等价于 bold，无单位|

## 1.5 文字样式 font-style

CSS 使用 `font-style` 属性设置文本风格。

```
p { 
font-style: italic; 
}
```

| 属性值    | 描述                      |
| ------ | ----------------------- |
| normal | 正常显示, 默认值，浏览器会显示标准的字体样式 |
| italic | *斜体*                    |

注意：平常很少给字体加斜体，而是给斜体标签（em,i）给位不倾斜字体。如下

```css
em{
    font-style: normal;
}
```

## 1.6 字体复合属性写法 font

将各种字体属性写在同一选择器下，节约代码。

```css
<style>
        /* 想要div 文字变倾斜 加粗 字号设置为16像素 并且是微软雅黑 */
        div {
            font-style: italic;
            font-weight: 700;
            font-size: 16px;
            font-family: 'Microsoft yahe';


            /* 复合属性：简写的方式  节约代码*/
            /* 顺序：font-style font-weight  font-size/line-height  font-family */
            font: italic 700 16px 'Microsoft yahei';
        }
</style>
```

规则

- **顺序：文字样式 文字粗细 文字大小 文字字体**
- 使用font属性时，必须按照上面语法格式中的顺序书写，**不能更换顺序**，并且各个属性间**以空格**隔开
- 不需要设置的属性可以省略(取默认值)，但必须保留`font-size` 和`font-family`属性，否则 font 属性将不起作用. 严格遵守顺序，且 `font-sieze` 和 `font-family` 必须有。

```css
body {
  font: 20px 'Microsoft yahei'
}
```

# 2 CSS文本属性

CSS Text（文本）属性定义文本外观，比如颜色、对齐、装饰、缩进、行间距等。

## 2.1 文本属性总结

| 属性              | 表示   | 注意                     |
| --------------- | ---- | ---------------------- |
| color           | 文本颜色 | 通常十六进制缩写               |
| text-align      | 文本对齐 |                        |
| text-indent     | 文本缩进 | 记住 `text-indent: 2em;` |
| text-decoration | 文本装饰 | 记住下划线和去除下划线            |
| line-height     | 行高   |                        |

## 2.2 文本颜色 color

`color` 属性定义文本颜色。

```
div {
  color: red;
color: #FF0000;
color: rgb(255，0，0);
}
```

实际开发中，最常用的是十六进制。

| 表示      | 属性值                          |
| ------- | ---------------------------- |
| 预定义的颜色值 | red，green，blue，pink等         |
| 十六进制 Hexadezimal    | #FF0000, #FF6600，#29D794     |
| RGB代码   | rgb(255，0，) 或rgb(100%，0%，0%) |
|HSL| hsl(0, 100%, 50%) |

## 2.3 对齐文本 text-align

`text-align` 属性用于设置元素文本内容的对齐方式。相当于html中的align对齐属性。

注意：是让盒子里面的文本内容水平居中， 而不是让盒子居中对齐

```
div {
  text-align: center;
}
```

| 属性值    | 解释      |
| ------ | ------- |
| left   | 左对齐（默认） |
| right  | 右对齐     |
| center | 居中对齐    |

例子： 

![](.\image\Chapter2_css_文字属性_003_文字对齐_例子.png)

## 2.4 装饰文本 text-decoration

`text-decoration` 属性规定添加到文本的修饰。可以给文本添加下划线、删除线、上划线等。

```
div {
    text-decoration: underline;
    text-decoration: overline;
    text-decoration: none;
}
```

| 属性值          | 描述                            |
| ------------ | ----------------------------- |
| none         | 默认，无装饰（最常用）. 无上划线， 无下划线， 无删除线 |
| underline    | 下划线，链接自带下划线（常用）               |
| overline     | 上划线。（几乎不用）                    |
| line-through | 删除线。（不常用）                     |

## 2.5 文本缩进 text-indent

`text-indent`定义段落首行缩进。通常是将段落的首行缩进

注意： 

- 通过设置该属性，所有元素的第一行都可以缩进一个给定的长度，甚至该长度可以是负值

- em是一个相对单位，就是当前元素(font-size)**1个文字的大小**

- 如果当前元素没有设置大小，则会按照父元素的一个文字大小

- 其属性值可为不同单位的数值、em字符宽度的倍数、或相对于浏览器窗口宽度的百分比%，允许使用负值。

- 建议使用em作为设置单位。 `em` 是一个相对单位，`1em` 就是一个字符所占大小。当 `text-indent=2em`，则恰好缩进两个文字。

- 1em 就是一个字的宽度。如果是汉字的段落，1em 就是一个汉字的宽度

```
div {
    text-indent: 10px;
}

p {
      /*行间距*/
      line-height: 25px;
      /*首行缩进2个字  em  1个em 就是1个字的大小*/
      text-indent: 2em;  
 }
```


# 3 文本属性: 高度

## 3.1 height 文本高度

## 3.2 行间距/行高 line-height 

`line-height` 设置行间的距离，行间距=文本高度+上间距+下间距

上下间距 是等值的。 改变行高的时候 是改变的上下间距的值， 文本的高度没有变化

line-height常用的属性值单位有三种，分别为像素px，相对值em和百分比%，实际工作中使用最多的是像素px

一般情况下，行距比字号大7--8像素左右就可以了。 line-height: 24px;

![](.\image\Chapter2_css_文字属性_001_文字行间距.png)

### 3.2.1 行高检测

`行高测量方法`行高我们利用最多的一个地方是：可以让单行文本在盒子中垂直居中对齐。

文字的行高等于盒子的高度。行高   =  上距离 +  内容高度  + 下距离。 上距离和下距离总是相等的，因此文字看上去是垂直居中的。

![](.\image\Chapter2_css_文字属性_002_文字行间距_行高检测1.png)

![](.\image\Chapter2_css_文字属性_002_文字行间距_行高检测2.png)

### 3.2.2 行高与高度的三种关系

- <mark>如果 行高 等 高度  文字会 垂直居中</mark>
.box {
    height: 200px; 
    /* 行高控制垂直居中 */
    line-height: 200px;
}

- 如果行高 大于 高度   文字会 偏下

- 如果行高小于高度   文字会  偏上

```
  /*line-height 要设置在font属性下面，否则无效，例如：*/
  height: 80px;
  text-align: center;
  font: normal bold 30px "宋体";
  line-height: 80px;
```

可以使用display:flex;布局方式让文字水平垂直居中

```
display: flex;
align-items: center;     /* 侧轴对齐方式*/
justify-content: center; /* 主轴对齐方式 */
```

## 3.3 vertical-align

### 3.3.1 vertical-align: middle


vertical-align：middle的作用机制就是对齐基线，这里之所以要设置line-height（最关键的）就是要让首行匿名元素（空白节点）处于父容器基线左右的位置，然后内联元素设置了vertical-align:middle才会对齐这个节点，否则是无效的！！！！

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



# 4 文本属性: 宽度 

## 4.1 width
`width: 5px`

https://www.zhangxinxu.com/wordpress/2016/05/css3-width-max-contnet-min-content-fit-content/

### 4.1.1 CSS2.1 中的尺寸体系 
#### 4.1.1.1 充分利用可用空间 (对应 CSS3 的 fill-available)
例如，一些`div`元素默认宽度100%父元素，这种充分利用可用空间的行为就称为“`fill-available`”。

#### 4.1.1.2 收缩与包裹 (对应 CSS3 的 fit-content)
典型代表就是浮动，绝对定位以及`inline-block`，英文称为“shrink-to-fit”，直译为“收缩到合适”，这种直译往往都是不准确的，这种行为表现确实很难描述，有些只可意会不能言传的感觉，而我自己一直以“包裹性”作为理解。在CSS3中有个专有的关键名称，`fit-content`.

#### 4.1.1.3 收缩到最小 (对应 CSS3 的 min-content)
这个基本上就出现在`table-layout`为`auto`的表格中，想必有经验的小伙伴一定见过下面这样一柱擎天的盛况的吧！

![](image/Chapter2_css_文字属性_width_001_一柱顶天.png)

大家空间都不够的时候，文字能断的就断，中文是随便断的，英文单词不能断。于是乎，第一列被无情地每个字都断掉，形成一柱擎天。这种行为称之为“preferred minimum width”或者“minimum content width”。

也就是本文的重点角色之一`min-content`，换了一个更加规范好听的名字了。
实际上，大家也看到了，`min-content`这种尺寸特性，`display:table-cell`实际上就有，但是，由于没有明确的名词或概念，大家都不知道，都是稀里糊涂有此表现，究其根本就不清楚了。

#### 4.1.1.4 超出容器限制 (max-content)
上面1~3情况，除非有明确的`width`相关设置，否则尺寸都不会主动超过容器宽度的，但是，存在一些特殊情况，例如，连续的英文数字，好长好长；或者内联元素被设置了`white-space:nowrap`，则表现为一江春水向东流。

例如下面：

.box {
    display: inline-block;
    width: 100px; height: 20px; 
    padding: 10px;
    background-color: #f0f3f9;
    white-space: nowrap;
}

_尺寸主动超过容器宽度，恰如一江春水向东流。_

`max-content`的表现与之有些类似，具有收缩特性，同时最大内容宽度。

#### 4.1.1.5 CSS3中重新对上面特性定义的好处 

好了，至此，大家会发现，`fill-available`, `max-content`, `min-content`, 以及`fit-content`确实在CSS2.1的时候，就有类似概念。

下面问题来了，既然CSS2.1这些特性都有了，那还要额外弄一些新值过来干嘛呢？岂不是白白增加学习成本啊？

好处: 
1.  方便某些布局的实现；
2.  **最重要的作用：** 在原有的display水平不变的情况下拥有元素其他display值才有的特性！
3.  让整个CSS世界的size体系更加直观和完善；

### 4.1.2 CSS3 中 width的属性值

#### 4.1.2.1 元素尺寸: 内部尺寸和外部尺寸
CSS中的元素尺寸分为两类，
一类叫做“内部尺寸”，英文写作”Intrinsic Sizing”，尺寸由内部元素决定；
还有一类叫做“外部尺寸”，英文写作”Extrinsic Sizing”，宽度由外部元素决定。


只有fit-available是外部尺寸；其余三个，都是根据内部内容来决定自己的宽度！！
fill-available 外部尺寸
max-content 内部尺寸
min-content 内部尺寸
fit-content 外部尺寸+内部尺寸



#### 4.1.2.2 总结
fill-availabele：设置的这个元素表现相当于没有设置样式的div，宽度自动充满父级
max-content：设置了这个属性的元素，会自动伸展或者收缩宽度，使自身宽度和最大宽度的子元素宽度一致
min-content：设置了这个属性的元素，会自动伸展或者收缩宽度，所有子元素 中 分别能收缩到 最小的宽度.  在这些 最小的宽度的数值里面,  取最大值, 作为min-content 的输出 




#### 4.1.2.3 width:fill-available
`width:fill-available`比较好理解，比方说，我们在页面中扔一个没有其他样式的`<div>`元素，则，此时，该`<div>`元素的`width`表现就是`fill-available`自动填满剩余的空间。也就是我们平常所说的盒模型的`margin`,`border`,`padding`的尺寸填充。

出现`fill-available`关键字值的价值在于，我们可以让元素的100%自动填充特性不仅仅在`block`水平元素上，其他元素，例如，我们一直认为的包裹收缩的`inline-block`元素上：

div { display:inline-block; width:fill-available; }

此时，元素兼具了块状元素的自动填充特性以及内联元素的定位对齐等特性。于是，（例如）我们就可以直接使用`line-height`让一个块状表现的元素垂直居中。

##### 4.1.2.3.1 例子
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

正如上面注释所提到的，FireFox浏览器下，目前(2016-05-20)不是标准的`-moz-fill-available`，而是`-moz-available`，估计过个几个版本可能会调整过来。

#### 4.1.2.4 width:max-content
`max-content`的行为表现可以这么理解，假设我们的容器有足够的宽度，足够的空间，此时，所占据的宽度是就是`max-content`所表示的尺寸。

##### 4.1.2.4.1 示例

您可以狠狠地点击这里：[CSS3 width:max-content对比测试demo](https://www.zhangxinxu.com/study/201605/width-max-content.html)

这是一个`display:inline-block`和`width:max-content`的对比demo，如果妹子下面的文字描述短，大家是看不出区别的。但是，如果文字内容像demo所展示的这么长, 会发现，<mark>`width:max-content`表现得好像设置了white-space:nowrap一样</mark>，文字一马平川下去，元素的宽度也变成了这些文字一行显示的宽度！

为什么会这么表现呢？定义就是这样的，对吧，我们对照下，首先，假设我们的容器有足够的空间，你想呀，容器足够空间，那下面的描述文字肯定一行显示了，此时，上面的图片和下面的文字那个内容宽度大，自然是文字啦，所谓`max-content`就是值采用宽度大的那个内容的宽度。

![max-content的表现对比示意](https://image.zhangxinxu.com/image/blog/201801/2018-01-10_005106.png)

#### 4.1.2.5 width:min-content
`min-content`宽度表示的并不是内部那个宽度小就是那个宽度，而是，采用内部元素最小宽度值最大的那个元素的宽度作为最终容器的宽度。

首先，我们要明白这里的“最小宽度值”是什么意思。
- 替换元素，例如图片的最小宽度值就是图片呈现的宽度，
- 对于文本元素
    - 如果全部是中文，则最小宽度值就是一个中文的宽度值；
    - 如果包含英文，因为默认英文单词不换行，所以，最小宽度可能就是里面最长的英文单词的宽度。


##### 4.1.2.5.1 对比例子
您可以狠狠地点击这里：[CSS3 width:min-content对比demo](http://www.zhangxinxu.com/study/201605/width-min-content.html)

1
同样的是和`display:inline-block`做比较，`display:inline-block`虽然也具有收缩特性，<mark>但宽度随最大长度长的那一个（同时不超过可用宽度）</mark>
<mark>而`width:min-content`的最终宽度是图片和文字最小宽度值里面大的那一个。</mark>

2 
在本例子中，图片的宽度最小值是256像素，不能再缩了；
而文字的最小宽度值是字符`display:inline-`所占据的宽度，因为`inline-block`后面的`block`可以换行，中文不用谈，天生被换行的命，显然`display:inline-`所占据的宽度要远远小于256像素，
因此，最终我们元素的宽度就是256像素，肉眼看到的就是自适应图片宽度的一个效果。在CSS2.1的世界里，这种效果实际上是不好实现的，要借助单元格特性。

![没有图片文字的最小宽度值](https://image.zhangxinxu.com/image/blog/201605/2016-05-20_014028.png)

下图为对比效果截图：

![min-content下的对比效果截图](https://image.zhangxinxu.com/image/blog/201801/2018-01-10_005340.png)

#### 4.1.2.6 width:fit-content
`width:fit-content`也是应该比较好理解的，“shrink-to-fit”表现，
换句话说，和CSS2.1中的`float`, `absolute`, `inline-block`的尺寸收缩表现是一样的。
<mark>display: inline-block元素默认是fit-content</mark> , 你如果不加上fill-available的话，红色背景应该是不会填充的


OK，然后，有小伙伴会疑问，既然跟很多CSS声明有一样的表现，那为什么还要再弄个新东西呢？

就拿水平居中效果举例，首先浮动肯定不行，因为只有左浮动和右浮动；绝对定位压根不占据空间，普通流中根本无法应用，而`inline-block`需要父级使用`text-align:center`，而本身可能还需要`text-align:left`略烦。

而`width:fit-content`可以没有这些烦恼，因为，`width:fit-content`可以实现元素收缩效果的同时，保持原本的block水平状态，于是，就可以直接使用`margin:auto`实现元素向内自适应同时的居中效果了。

##### 4.1.2.6.1 例子
您可以狠狠地点击这里：[CSS3 width:fit-content使用与margin auto下水平居中demo](https://www.zhangxinxu.com/study/201605/width-fit-content.html)

结果，简简单单就居中了，也不要担心其他元素会跟在后面一行显示了：

![收缩表现下margin:auto居中效果](https://image.zhangxinxu.com/image/blog/201801/2018-01-10_005451.png)

## 4.2 horizontal-align 

# 5 自定义variable/ Custom Properties
CSS Variablen heißen Custom Properties.
- Sie werden wie folgt vereinbart： `--variablen-bezeichner: wert`
- Der Aufruf erfolgt über eine Funktion.: `var(--variablen-bezeichner)`

说明
- 自定义variablet通常定义为 globale Variablen， die  im :root vereinbart werden.
- Sollen die Variablen mit anderen Dateien (z.B. js) später verändert werden, dann müssen Custom Properties verwendet werden 
- keine Sass Variablen.

例子: 
```css
:root{

    /* Deklaration*/
    --main-hue: 240;

    /* Deklaration und Aufruf.
    Verändern Sie den Wert für --main-hue und schauen Sie, was passiert.
    Der hue kann einen Wert zwischen 0 und 360, jeweils inklusive annehmen.
    Der Variablenaufruf erfolgt über die Funktion var()
    In der Parameterliste werden dann die Werte, oder
    wie folgt auch Variablen angegeben.

    */

    --main-color: hsl(var(--main-hue),100%,50%);
    --secondary-color: hsl(var(--main-hue), 100%, 20%);
    --tertiary-color: hsl(var(--main-hue), 100%, 90%);

}

  

h1,
h2,
h3{

    /* Aufruf */
    color: var(--secondary-color);
    background-color: var(--tertiary-color);

}

  
article{
    background-color: var(--secondary-color);
    color: var(--tertiary-color);
}
```