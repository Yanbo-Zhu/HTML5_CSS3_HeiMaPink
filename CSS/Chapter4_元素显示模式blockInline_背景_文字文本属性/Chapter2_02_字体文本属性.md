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

## 2.3 对齐文本(水平方向) text-align

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


# 3 列表属性
## 3.1 list-style
```css
ul{
    list-style: none; 
}
```

none 代表 列表左边的的 点 或者 数字, 不再被显示了
![](image/Chapter2_css_列表属性_001_list-style.png)

## 3.2 例子: 列表去掉左边的点 和 左边的空间

```html
        <nav>
            <ul>
                <li><a href="#aufbau">Aufbau</a></li>
                <li><a href="#farben">Farben</a></li>
                <li><a href="#variablen">Variablen</a></li>
                <li><a href="#schrift-aufbau">Schriftaufbau</a></li>
                <li><a href="#block-inline">Block vs Inline</a></li>
                <li><a href="#bsp-block-inline">Beispiel für Block- und Inline Elemente</a></li>
                <li><a href="#margPad">Margins und Paddings</a></li>
                <li><a href="#box-sizing">box-sizing</a></li>
            </ul>
        </nav>
```

```css
p{
    max-width: 60ch;
}

nav ul{
    list-style: none;
    padding: 0;
}

nav li{
    background-color: hsla(182,0%,80%,1);
    margin: 1% 0;
    text-align: center;
}

  
nav a{
    display: block;
}
```
